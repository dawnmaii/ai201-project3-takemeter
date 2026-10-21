# Acceptance criteria — TakeMeter

---

## 1. Overall 75% accuracy on the test split

On each of the three seeds, the classifier should achieve 75% accuracy (23 out of 30 posts) on the test split.

**Why this target:**
Especially in a subreddit, a post's title and its body often say different things and by themselves can be labeled differently, so a model reading the text can be pulled towards the wrong label. I can't expect perfect accuracy on the test split; with about 30 test posts, one post is about 3.3 points, so 75% allows 7 mistakes. Chance is about 33%, so 75% is well above a guess. Anything higher would only allow for fewer mistakes and less room for a mismatch, which isn't guaranteed for my model.

---

## 2. 20/30 agreement on labeling posts

My labels under the staff taxonomy match the staff labels on at least 20 of the 30 posts.

**Why this target:**
Posts on this subreddit cover a variety of topics in a variety of writing styles, and since I'm using staff taxonomy, it's more likely my labels will differ from staff's. I expect to disagree with staff on the `analysis` and `hot_take` labels. Staff also expect a rate in the 70s, and 20 out of 30 = 67%. It's under the staff's expected range, but since it's their taxonomy and not mine, I'm going to give a bit more room for error.

---

## 3. Every label has at least 60 posts

Based on `labels.csv`, every label should have at least 60 posts classified under it.

**Why this target:**
60 is below the ceiling that all three labels can meet with 200 posts while leaving some room (the ceiling is 66). This leaves me with 180 labeled posts, and the 20 extra posts can go to any label, which gives about 9 posts in the test split. The notebook will flag any label with fewer than 8 posts in the test split, so the 60-post minimum allows for a readable test split, even if it is noisy.

---

## 4. F1 of at least 0.60 on test split

Every label has an F1 of at least 0.60 on the test split, on each of the three seeds.

**Why this target:**
Three labels means chance is about 0.33 for a random guess, and 0.60 is well above that. The smallest label has about 9 test posts, so its score is noisy, and 0.70 would let luck fail a good model. A 0.60 floor for all three labels still means the model finds most of that label's real posts without calling too many other posts by that name. It stops one bad label from passing on accuracy alone. An F1 at 0.60 catches that bad label, regardless of whether or not the overall target passes.

---

## 5. 0.6 confidence level with 80% correct labeling, 50% if otherwise below 0.6

On each of the three seeds, per test split, classifier predictions at 0.6 confidence or above are correct at least 80% of the time. Unsure predictions below the 0.6 threshold should be correct at most 50% of the time.

**Why this target:**
With three labels, the lowest the model's top confidence can be is about 0.33. The lower the threshold, the more posts the model is confident about. At 0.6, I expect at least 15 test posts landing in the confident group for the 80% to mean something; the 80% is a 5-point margin over the 75% overall target (criterion 1). I set the unsure group's ceiling at 50% so confident predictions are clearly more reliable than unsure ones. Unsure predictions are allowed to be better than a guess, up to 50%, but should clearly be less reliable than confident ones.

---

<!-- ─────────────────────────────────────────────────────────────────────────
     UNIT 6 — read this before you change anything above.

     If a criterion turns out to be BROKEN rather than merely unmet, you can
     revise it, and that earns credit. But never delete or edit the original
     line. Add the revision underneath, like this:

         ## 2. Every label performs acceptably

         The model performs well on all labels.

         **Why this target:** ...

         > **Revised in unit 6:** Every label has an F1 of at least 0.60 on
         > the held-out set.
         >
         > **Why revised:** "performs well" gave me nothing to check. I
         > couldn't produce a verdict from it at all.

     That's a revision because the criterion couldn't be MEASURED.

     Lowering a target because you missed it is not a revision, and it costs
     you the point:

         ✗ "Overall accuracy of at least 0.65" → "at least 0.55", because
            0.65 turned out to be optimistic for 200 examples.

     A number you missed stays where it is, gets diagnosed, and gets a fix
     attempted. That's where the points are.
     ───────────────────────────────────────────────────────────────────────── -->
