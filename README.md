# TakeMeter

---

## What This Does

TakeMeter sorts posts from r/Seattle, a public subreddit about Seattle, WA, into three labels. `report` covers a specific event or fact, or a link to a news article. `opinion` covers a view or rant with nothing checkable behind it. `heads_up` covers a message addressed to a stranger or to the community, such as a lost-item notice, a warning, or a note of sympathy.

---

## Label Taxonomy

### `report`

**Definition:** a verifiable post that can be checked against public record and names a specific event, date, or source.

**Example 1:**
> "Seattle Sued Again Sued Again For Teenagers Death at Gas Works Park"
>
> <https://www.seattletimes.com/seattle-news/seattle-sued-again-for-teenagers-death-at-gas-works-park/>
>
> The family of a 15-year-old who fell to his death at Gas Works Park last summer is again suing the city for failing to maintain and secure the park’s towering coal plant structure, despite decades of evidence pointing toward serious safety concerns.

**Example 2:**
> "Ballard Link Community Forum was packed"
>
> Even more people than the last one 6 months ago, completely filling the Nordic Museum's Great Hall with a large contingent forced to stand. Impressive organizing efforts by Save Ballard Rail. A good turn out of local politicians, including city council members Strauss (obviously) and Rinck, as well as Mayor Wilson. ST CEO Constantine made it this time.
>
> My takeaways:
>
> The narrative ST is presenting is that they are continuing with the course as it was planned without the budget shortfall, with the hope that they figure the finances out before they have to start paying for items that are unfunded. The first such deadline is in 2030.
>
> They are committed to not making any major changes to the project, and effectively disregarded any of the bolder budget saving ideas that have been floated (automated light metro, elevated through downtown, delay the second tunnel, etc.). They claim to have considered them internally, but determined that the options are either "infeasible" or do not offer much in the way of savings, though details were limited.
>
> ST hopes to save costs with, design tinkering, construction efficiencies, and dropping stations. Basically what was done with WSLE. SLU station seems functionally done already: it's cut from the current plan, and they don't appear to have the appetite to try and revive it.
>
> They also will look to use new financing tools, in particular 75-year bonding authority from the state was discussed.
>
> They didn't give a detailed break down, but the implication was that the above would still not be enough to close the gap. Ultimately it seems their big hope is that they will get bailed out by a more transit friendly federal government. All politics is national now, I guess.
>
> Crowd did not like CEO Constantine, strongly applauding shots taken at him by questioners.

### `opinion`

**Definition:** a post that is not verifiable, for example an anecdote based on personal experience.

**Example 1:**
> "A window into the opinions of the wealthy on the light rail."
>
> My former partner’s family is a part of the wealthy culture of the eastside. I am a regular Joe who grew up solidly middle class and worked a physically demanding but popularly considered “noble” profession for most of my life.
>
> I had the opportunity to be a fly on the wall for many dinner party conversations over that past several years on the topic of the light rail and what the zeitgeist of that spectrum of people held as it applies to light rail as well as other things. God I hope I used that word correctly, please don’t eat me.
>
> Pre-completion of the light rail, the discussion always focused on how it would be underutilized, how it was a big waste of taxpayer dollars, and the disruption construction caused to motor vehicle traffic.
>
> Obviously it was a disruption to traffic, and the construction over the floating bridge had some major issues. Such is the cost of development and a realized risk of being the first to engineer a train over a floating bridge in the whole world.
>
> The underutilization though I thought was very interesting in how the dinner party conversation shifted after project completion. No longer could they claim no one would use it since now the park and ride locations, at least where I have used them and heard reports, on the eastside are packed with many additional vehicles still searching for a spot by mid morning on Tues, Wed, Thurs. At this point the dinner talk began to be about how they wouldn’t want to share a packed train car with “smelly” strangers. Which are preferences and some people have sensitivities that public transport can affect and my point here isn’t to evangelize trains, there are plenty of places you can get that.
>
> However my take away is that in these circles they did not want to take in new information that was counter to their original assumptions and instead shifted the goalposts to their own personal aversion to utilizing public transit. This particularly bothered me because it would often be bookended by conversations about how non-specialized workers in areas of the eastside would demand higher wages, which obviously the people could afford, they would just have fewer luxury goods attributed to them as individuals if their business was more fairly distributing its profits. The train provides a fast, reliable(mostly), and efficient transportation for non-specialized workers to be able to live in a lower COL area and still be able to work in and provide services for the wealthy eastside enclaves. Which would directly benefit these same people who are the owners of said businesses by reducing the pressure for higher wages by a vastly increased pool of potential employees.
>
> I could go on with my rant but I gotta do some laboring now. I’m probably just a bit bitter at holding back from a more confrontational approach in those moments due to wanting to keep the peace. The experience of being in a wealthy environments after having done physical labor actually kind of put me off the idea of wanting many of the luxury items of the wealthy as it really showed me that fast cars and fancy clothes or whatever luxuries you’re into pales in comparison to less status based pursuits in life. At least for me. Ok back to the grindstone.

**Example 2:**
> "Greenwood Fred Meyer can afford an inventory robot yet is selling moldy produce"
> Idk maybe hire more actual people and maybe this wouldn’t happen…but what do I know

### `heads_up`

**Definition:** a PSA, or a post directly addressing something to the community or a stranger in the community.

**Example 1:**
> "Your car was towed for blocking a driveway"
> How tragic

**Example 2:**
> "Free Event"
> Come support the local youth cheerleading team and enjoy our fall festival.

### The hardest boundary

**Which two labels:** `heads_up` and `opinion`, plus the `report`/`heads_up` boundary

**The decision rule I used every time:**
If it's addressed to a stranger in the community (ex. "to the person who...") or the community in general WITHOUT an opinion or view of its own, it's a `heads_up`. If the post is addressed to the community and also states a view, it's an `opinion`. If the post can be checked against a record and names a specific event, date, or source that you could look up, it's a `report`. A post can argue and still be a `report` if it names a checkable figure or source. Anything else is `opinion`.

---

## The Dataset

**Where the posts came from:** the r/Seattle subreddit.

**How I labelled them:** I read each post and its content, then checked with my initial labeling definitions to determine the final label. I decided to add a tie-break after labeling the cold set so it was easier to distinguish between an `opinion` post and a `heads_up` post. I then had AI pre-label the posts that were not in the cold set. I read all 286 AI pre-labels, corrected 34 (denoted with "corrected" in the csv file in the "note" column), and accepted the other 252 as they were.

**Counts per label:**

| Label | Count | Share |
| --- | --- | --- |
| `report` | 38 | 12% |
| `opinion` | 88 | 28% |
| `heads_up` | 189 | 60% |
| **Total** | 315 | 100% |

### Four hard cases

**1.**
> *The post:* I paid a drummer to follow the annoying preacher around. Totally worth it.
>
> *Could have been:* `report`
>
> *I chose, because:* `opinion`, since the post is not directed at anyone in particular, nor does it have an event, date or source you could look up.

**2.**
> *The post:* Ballard Link Community Forum was packed.
>
> *Could have been:* `opinion`
>
> *I chose, because:* `report`, because the event was named, and its location was specific.

**3.**
> *The post:* Did your dog recently bite me?
>
> *Could have been:* `report`
>
> *I chose, because:* `heads_up`, since the rule checks addressed-to-someone first. OP made a specific request to a stranger in the community for the dog's vaccination records.

**4.**
> *The post:* What do you guys think about buying a condo in this Seattle market?
>
> *Could have been:* `heads_up`
>
> *I chose, because:* `opinion`, because even though the title addresses the community (rule 1), OP's opinion on the housing market was what led to the question (rule 2). It is not a question alone.

---

## The Training Run

**Base model:** distilbert-base-uncased

**Settings:**

- device: cpu
- torch: 2.14.1+cpu
- epochs: 3
- learning rate: 2e-5
- batch size: 16
- seed: 42
- max length: 128

**Anything I changed from the defaults, and why:** N/A for unit 5. In unit 6 I added class weights to the loss (see The Improvement).

**Split sizes:**

| Label    | Train | Val | Test |
|----------|-------|-----|------|
| opinion  | 62    | 13  | 13   |
| report   | 26    | 6   | 6    |
| heads_up | 131   | 29  | 29   |
| TOTAL    | 219   | 48  | 48   |

There were few `report` posts to begin with, hence the split size being 6 test posts. Since it's under the 8-post guideline, its scores will be noisy.

Upon the first run (took 3 minutes 27 seconds), validation accuracy stayed at 0.604 across all three epochs, which is the `heads_up` share. Macro F1 stayed at 0.251. My best guess is because `heads_up` posts made up over half the posts, so the model focused only on the `heads_up` label. Would like to test two potential fixes to this:

1. Using more epochs first to allow the model more passes over the training data. With this fix, I predict the model would make more `opinion` and `report` predictions on posts.
2. Adding class weights to the loss so the model would stop defaulting to the `heads_up` label and predicts `report` and `opinion` posts as those labels.

This is the "before" run for unit 6. The class-weights fix (fix 2 above) is the one I tested in unit 6; see The Improvement.

---

## How I Used AI

### Moment 1

- *What I asked for:* I asked for AI to pre-label the remaining posts that were not in the cold set, after defining my tie-breaking rules and requested format for the output: each row marked "pre-labelled" in notes.
- *What came back:* A label for every row, with the note column marked. I checked the output for valid labels and exact spelling.
- *What I changed:* I read every AI pre-label, corrected 34 of them (marked "pre-labelled, corrected" in notes), and accepted the other 252. The 20 cold posts were labeled by me without AI use.

### Moment 2

- *What I asked for:* I asked AI to review each of the five criteria for understanding and checkability by someone who couldn't ask me what I meant, as well as whether the numbers behind each criterion made sense given my data.
- *What came back:* Multiple problems were flagged throughout. For example, criterion 3 was initially set to 75 posts per label minimum. That was impossible with 200 initial posts and three labels. AI didn't write any criteria for me.
- *What I changed:* I fixed the arithmetic, and the criteria and reasons are my own. Later I revised criterion 3 to 30 posts, with a stated reason, before training.

**Pre-labelling disclosure:** I had AI pre-label the posts that were not included in the cold set, after which I went through every AI pre-label and corrected those I didn't agree with. Anything without a "corrected" or "cold" keyword in the notes column has been pre-labelled by AI and approved by me.

### Moment 3

- *What I asked for:* I asked AI to check the criterion 5 diagnosis for accuracy against the threshold numbers in `results_three_seeds_before.json`.
- *What came back:* A flag that "the gap between the groups is small" was wrong. The confident and unsure groups differ by 20 to 40 points, so the model's confidence does separate right answers from wrong ones. The real problem is that the confident group isn't reliable enough to reach 80%.
- *What I changed:* I rewrote the criterion 5 verdict and the Diagnoses sentence to say that.

### Moment 4

- *What I asked for:* I asked AI to implement the class-weights change from my diagnosis, in the training function of the notebook.
- *What came back:* A `WeightedTrainer` subclass that overrides the loss, and a function that computes balanced weights from the training split only.
- *What I changed:* I ran the notebook, hit a `NameError` for `evaluate` after a kernel restart, and fixed it by re-running the definitions and restoring `results.json` from git so the committed before-run file wasn't overwritten. The loss code was drafted with AI; the run order and the restore were mine.

---

## Baseline vs. Trained

| Measure | Baseline | Trained | Difference |
| --- | --- | --- | --- |
| Overall accuracy | 0.667 | 0.604 | -0.062 |
| Macro F1 | 0.641 | 0.251 | -0.390 |
| F1 — `heads_up` | 0.737 | 0.753 | +0.016 |
| F1 — `opinion` | 0.519 | 0.000 | -0.519 |
| F1 — `report` | 0.667 | 0.000 | -0.667 |

**What I predicted before I looked:**
I expect the trained model to beat the baseline for the `heads_up` posts, since 60% of posts I collected were labeled as `heads_up`. The baseline wins on `report` and `opinion` posts since it read the definitions.

**What the gap actually means:**
Fine-tuning added nothing in this run, since the baseline beat the trained model on accuracy (0.667 vs 0.604 for the trained model) and on macro F1 (0.641 vs 0.251). The trained model also scored 0.000 on `report` and `opinion`; the two labels where the baseline scored 0.667 and 0.519. Then again, the baseline isn't good either, with only 0.667 accuracy compared to the 0.75 target criterion 1 asks for. Its `report` score is also noisy because the test split was below the recommended 8 posts for the notebook, and the F1 score for the `opinion` posts is below the 0.60 target, at a score of 0.519. The trained model gets a 0.753 F1 score for `heads_up` only because it predicts `heads_up` for every post, and a 0.016 gap on 48 posts is within noise.

---

## Run Log — Before

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
| --- | --- | --- | --- | --- | --- |
| 1. Accuracy | >= 0.75 | 0.604 | 0.604 | 0.604 | MISSED |
| 2. Staff agreement | >= 20/30 | 19/30 | same | same | MISSED |
| 3. >= 30 posts per label | >= 30 | 38 / 88 / 189 | same | same | MET |
| 4. F1 >= 0.60 each label | >= 0.60 | report 0.000, opinion 0.000, heads_up 0.753 | same | same | MISSED |
| 5. Confidence | ≥ 80% correct at 0.6+, ≤ 50% correct below 0.6 | 0.6+: 74% (27) · below: 43% (21) | 0.6+: 77% (30) · below: 33% (18) | 0.6+: 62% (29) · below: 58% (19) | MISSED |

After the first run, I added a threshold measurement to evaluate (section 5) so criterion 5 could be tested at 0.6. Targets are unchanged. Accuracy and the confusion matrix are the same as the first run.

### Confusion matrix

| true \ predicted | opinion | report | heads_up |
| --- | --- | --- | --- |
| **opinion** | 0 | 0 | 13 |
| **report** | 0 | 0 | 6 |
| **heads_up** | 0 | 0 | 29 |

**My biggest off-diagonal number, and what it means:**
On seed 42, 11 of 13 real `opinion` posts are called `heads_up`, the biggest off-diagonal number. The model never predicts `report` on seed 42, and 5 of 6 real `report` posts are called `opinion`. On seed 7 the model predicts `report` but never `opinion`, and on seed 2024 it predicts both. Most of its guesses on both seeds still go to `heads_up`.

### Confusion matrix — after (seed 42)

| true \ predicted | opinion | report | heads_up |
| --- | --- | --- | --- |
| **opinion** | 2 | 0 | 11 |
| **report** | 5 | 0 | 1 |
| **heads_up** | 3 | 0 | 26 |

---

## Verdicts and Diagnoses

| # | Criterion | Target | Verdict | How I decided |
| --- | --- | --- | --- | --- |
| 1 | Accuracy | >= 0.75 on all seeds | MISSED | 0.604 on all three seeds, all 13+6 `opinion` and `report` posts predicted as `heads_up` |
| 2 | Staff agreement | ≥ 20 of 30 posts match staff | MISSED | Count posts where my label under the staff taxonomy matches data/staff_labels.csv. My agreement with staff was 63% (19 of 30). |
| 3 | Balance | >= 30 posts per label | MET | `labels.csv` has 38 `report`, 88 `opinion`, 189 `heads_up` |
| 4 | F1 | >= 0.60 each label | MISSED | `report` and `opinion` are 0.000 on all three seeds, `heads_up` is 0.753 |
| 5 | Confidence | ≥ 80% correct at 0.6+, ≤ 50% correct below 0.6 | MISSED | The confident group is 62–77% correct on all three seeds, below the 80% target, and the unsure group is 58% correct on seed 2024, above the 50% limit. The model's confidence ranks its answers somewhat, but not reliably enough to meet the target. Source: threshold block in results_three_seeds_before.json. |

### Diagnoses

Missed criteria 1, 4, and 5. The cause is that 315 posts is too small a dataset for three labels (cause 4), and there are only 38 `report` posts (cause 1). Every row in the confusion matrix lands on `heads_up`, and the 0.604 accuracy equals the `heads_up` share of the test split (29 of 48) on all three seeds. The model never learned to separate the labels, and the collapse is the same on every seed, so the split isn't the cause. Its confidence ranks its answers somewhat, but the confident group isn't reliable enough to meet the 80% target. The 0.6 threshold isn't the cause.

Missed criterion 2 (19/30 agreement against a target of 20). The cause is a boundary I applied inconsistently (cause 2). Nine of the eleven disagreements are pile (a): the staff rules answered the question and I applied them loosely. Most of them are Rule 1, where I read a checkable number as decoration. Eight of the ten posts staff labeled `analysis` I labeled differently. Two disagreements (sp_010 and sp_020) are ambiguous, so I'd argue my reading there. The miss is mostly in how I applied the rules, not in the rules themselves.

---

## Agreement Report

**Agreement rate:** 19/30 = 63%

### Disagreement Analysis

### 1. (sp_003)

> *The post:* "The club championship scoring changed in 2019 from top-6 to top-10. Since then our B team has finished above the A team twice. That's not depth improving, it's the scoring rewarding turnout."
>
> *Staff said / I said:* `analysis` / `reaction`
>
> *My call, and why:* `analysis`. Rule 1: the 2019 rule change and the B team result carry the argument.
>
> *Which pile:* (a)

### 2. (sp_004)

> *The post:* "Everyone blames the hill at 18 miles. I split the field into people who ran the first half under 1:45 and over, and the slowdown after 18 was almost identical for both groups. If the hill were the problem the fast starters would fall apart harder."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* `analysis`. Rule 1: the 1:45 split and the comparison of slowdowns carry the argument. The writer doesn't just assert that the hill isn't the cause; the comparison is the test, and the number is what the conclusion rests on.
>
> *Which pile:* (a)

### 3. (sp_005)

> *The post:* "Carbon plates aren't the whole story. My times dropped 2% in the shoes and another 2% the following year in the same pair, when the only thing that changed was going from 35 to 50 miles a week."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* `analysis`. Rule 1: the two 2% drops are comparable numbers, and the claim that mileage, not shoes, changed the times rests on them. The fact is load-bearing, not decoration.
>
> *Which pile:* (a)

### 4. (sp_006)

> *The post:* "Checked the entry lists. 41% of this year's field have never run the distance before, against 26% five years ago. That's why the finish-line photos look different, not because standards dropped."
>
> *Staff said / I said:* `analysis` / `reaction`
>
> *My call, and why:* `analysis`. Rule 1: the 41% and 26% figures are used to reject a rival explanation (standards dropping), so the numbers carry the argument.
>
> *Which pile:* (a)

### 5. (sp_007)

> *The post:* "Ran the same loop in 4C and in 24C within a fortnight, same effort by heart rate. 90 seconds slower in the heat over six miles. People keep saying heat costs you 'a bit' and it's more than that."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* `analysis`. Rule 1: the 90-second difference over six miles is a measured comparison, and the claim that heat costs more than people say rests on it.
>
> *Which pile:* (a)

### 6. (sp_008)

> *The post:* "Went back through the club results going back to 2012. Every single year the number of people who enter the spring marathon and don't start it sits between 18 and 23 percent. It's not a bad-luck year, it's the base rate."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* `analysis`. Rule 1: the 18–23% range across named years is the fact the argument rests on, and it's used to rule out a one-off explanation. Without the numbers, the claim is a hot take.
>
> *Which pile:* (a)

### 7. (sp_009)

> *The post:* "The 10K route was remeasured in 2021 and came out 60 metres long. Everyone comparing PBs from before and after that is comparing two different races, which is about 12 seconds at club pace."
>
> *Staff said / I said:* `analysis` / `reaction`
>
> *My call, and why:* `analysis`. Rule 1: the 60-metre remeasurement and the 12-second effect are the facts the argument rests on, and they aren't decoration.
>
> *Which pile:* (a)

### 8. (sp_010)

> *The post:* "Three of us ran the same session on the same day, different shoes, within 10 seconds of each other over 5 miles. I'm not saying shoes do nothing, but whatever they do was smaller than the noise between three people."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* `analysis` is the stronger reading, though `hot_take` is defensible. Rule 1: the three-runner comparison is checkable, and the claim that shoes do less than the noise between runners rests on it.
>
> *Which pile:* (c)

### 9. (sp_013)

> *The post:* "The club needs to stop pretending the Tuesday session is for everyone. It isn't and it never has been."
>
> *Staff said / I said:* `hot_take` / `reaction`
>
> *My call, and why:* `hot_take`. Rule 2: the post is about the club as a whole ("The club needs to stop pretending…"), not about the writer's experience, so it's a general claim. It offers no support, so staff's label applies.
>
> *Which pile:* (a)

### 10. (sp_017)

> *The post:* "Road racing peaked in about 2015 and everything since has been marketing."
>
> *Staff said / I said:* `hot_take` / `reaction`
>
> *My call, and why:* `hot_take`. Rule 2: "everything since has been marketing" is a general claim about the sport and nothing about the writer's own recent experience. The year is part of the assertion, not evidence for it, so the post is unsupported.
>
> *Which pile:* (a)

### 11. (sp_020)

> *The post:* "Every injury thread on this forum is the same injury and the same three replies."
>
> *Staff said / I said:* `hot_take` / `reaction`
>
> *My call, and why:* `hot_take`, though it's close. Rule 2: the post makes a general claim about every injury thread on the forum, not a report of the writer's own experience. It sounds observational, but it gives no count, so the claim is asserted, not shown. Staff flagged it as hard for this reason.
>
> *Which pile:* (c)

**What the pattern in my disagreements tells me:**
Eight of my eleven disagreements are posts staff labeled `analysis`, and I labeled only two of staff's ten `analysis` posts `analysis`. Nine of the eleven fall in pile (a), so most of my misses are a consistency problem, not a gap in the taxonomy. Most of them are Rule 1: I read a checkable number as decoration when it carried the argument (sp_004, sp_005, sp_006, sp_007, sp_008). Two are Rule 2 misses on posts I labeled `reaction` that staff called `hot_take` (sp_013, sp_017). Two calls are genuinely ambiguous (sp_010, sp_020), where I'd argue my reading.

---

## The Improvement

**What I changed:** Added class weights to the training loss, weighted by `n / (k × count)` (balanced to each label's frequency in the training split), so a missed report or opinion costs more than a missed `heads_up`. Everything else stayed the same: base model, 3 epochs, learning rate 2e-5, batch 16, and the same three seeds.

**Which diagnosis pointed at it:** The collapse. On all three seeds the model predicts `heads_up` for every test post, the validation loss on seed 42 only falls from 0.89 to 0.83 over three epochs. That suggests more epochs alone won't change the predictions, while class weights target the cause the matrix shows: `heads_up` is the cheapest answer to the loss.

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
| --- | --- | --- | --- | --- | --- |
| 1. Accuracy | >= 0.75 | 0.583 | 0.604 | 0.562 | MISSED |
| 2. Staff agreement | >= 20/30 | 19/30 | same | same | MISSED |
| 3. >= 30 posts per label | >= 30 | 38 / 88 / 189 | same | same | MET |
| 4. F1 >= 0.60 each label | >= 0.60 | `opinion` 0.174, `report` 0.000, `heads_up` 0.776 | `opinion` 0.000, `report` 0.364, `heads_up` 0.750 | `opinion` 0.190, `report` 0.500, `heads_up` 0.687 | MISSED |
| 5. Confidence | 80% at 0.6+, 50% below | 0.6+: no posts; below: 58.3% (48) | 0.6+: no posts; below: 60.4% (48) | 0.6+: no posts; below: 56.2% (48) | MISSED |

**Did it help, and how do I know:**

Partly. Macro F1 rose on all three seeds, from 0.251 to 0.317, 0.371 and 0.459, and the model now predicts `report` and `opinion` on some posts. But accuracy fell on seeds 42 and 2024 and stayed the same on seed 7, and no criterion moved to MET. The macro F1 gain depends mostly on `report`, which has six test posts per seed, so a change of one or two posts moves it a lot. I wouldn't call this run better without more data. The clearest change is in the matrix: `report` posts are now sometimes predicted as `report` (seeds 7 and 2024), where before the model never predicted it.

---

## What's Still Broken

**Criterion 1 (accuracy ≥ 0.75).** Still missed on every seed, at 0.56 to 0.60. Next I'd collect more labeled posts before changing the training again, since 315 posts limit what any setting can learn here. I stopped at one change because the unit allows one, and a single measured change is easier to read than several untested ones.

**Criterion 2 (staff agreement ≥ 20/30).** Still missed at 19/30. This is about my labels, not the model. The next step is to re-read the eleven disagreements against Rule 1 and Rule 2, starting with sp_004 to sp_008, and to label future posts with those rules in front of me. I didn't re-label after seeing the staff labels, so 19/30 is the count on my original labels.

**Criterion 4 (F1 ≥ 0.60 on each label).** Still missed on every seed. `opinion` ranges from 0.000 to 0.190 and `report` from 0.000 to 0.500. Both labels have few test posts, so these scores are noisy, but none reaches the target. The next step is more `report` and `opinion` posts, since the label counts are the limit here.

**Criterion 5 (confidence).** The class weights spread the model's probability across three labels, so none of its predictions reach 0.6 confidence on any seed. The 80% half can't be tested, and the below-0.6 group is above 50% on all three seeds. Next I'd look at whether milder weights help, or whether the criterion needs a different measure of confidence. I stopped here for the same reason as criterion 1.

**The gap between what I meant my labels to capture and what the model
learned:**

I meant `report` to capture a post that can be checked against a public record. The model learned that `report` is rare: on seed 42 it never predicts `report`, and it sends most real `report` posts to `opinion`. I meant `opinion` to capture an unverifiable personal anecdote. The model learned to send most of those posts to `heads_up`, the majority label. On seed 2024 it predicts all three labels, and on seed 7 it predicts `report` but never `opinion`. Most of its guesses on both seeds still go to `heads_up`, so what it learned is closer to "this post is probably `heads_up`" than to the distinctions I wrote down.

---

📖 **How to run this project: [RUNNING.md](RUNNING.md)**
