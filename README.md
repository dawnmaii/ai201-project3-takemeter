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

**Anything I changed from the defaults, and why:** N/A

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

This is the "before" run for unit 6.

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

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy |  |  |  |
| Macro F1 |  |  |  |
| F1 — `label_one` |  |  |  |
| F1 — `label_two` |  |  |  |

**What I predicted before I looked:**
<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->

**What the gap actually means:**
<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->

---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

| true \ predicted |  |  |  |
|---|---|---|---|
| **** |  |  |  |
| **** |  |  |  |
| **** |  |  |  |

**My biggest off-diagonal number, and what it means:**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->

---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |
| 3 |  |  |  |  |
| 4 |  |  |  |  |
| 5 |  |  |  |  |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->

---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate:** ___/ 30 =___%

<!-- Nobody grades this number. A 60% who argues every disagreement from the
     stated rules beats a 95% who wrote "staff was right" nine times. Several
     of the 30 were chosen because they're genuinely ambiguous — you should be
     winning some of these. -->

**Disagreements**

<!-- Three lines each: the post, both labels, and who you think is right and
     why — grounded in the staff definitions you were both applying.

     Then sort each into one of three piles:
       (a) the rule covered it and I applied it loosely → a consistency problem
       (b) the rule genuinely doesn't say               → a gap in the definitions
       (c) the rule is ambiguous here and my reading is defensible → argue it.
           This is a legitimate win.

     Pile (a) is the one that matters most for your diagnosis: if you applied a
     written rule two different ways on 30 posts, that is direct evidence about
     what you did across your own 200. -->

**1.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**2.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**What the pattern in my disagreements tells me:**

---

## The Improvement

**What I changed:**

**Which diagnosis pointed at it:**

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->

---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->

**The gap between what I meant my labels to capture and what the model
learned:**
<!-- Two sentences. Your confusion matrix is the evidence. -->

<!-- ═════════════════════════════════════════════════════════════════════

     SUBMISSION CHECKLIST — unit 5

       [ ] criteria.md has five numbered criteria, each naming a NUMBER
       [ ] Each has a reason underneath tied to your data or taxonomy
       [ ] labels.csv: at least 150 rows, text/label/note, ONE file not split
       [ ] No label above 70%
       [ ] All five unit 5 sections have real content
       [ ] Label Taxonomy includes the decision rule for your hardest boundary
       [ ] The Dataset includes three hard cases
       [ ] results.json and test_split.csv committed (the notebook does this)
       [ ] At least four new commits
       [ ] Repository URL submitted — WRITE IT DOWN

     SUBMISSION CHECKLIST — unit 6

       [ ] Baseline vs. Trained table, with your prediction written beforehand
       [ ] Run Log — Before, five criteria across three seeds
       [ ] Confusion matrix TYPED AS A MARKDOWN TABLE
       [ ] A verdict on every criterion
       [ ] A diagnosis for every miss, using the agreement report as evidence
       [ ] Agreement Report with every disagreement adjudicated
       [ ] One improvement, with Run Log — After
       [ ] What's Still Broken
       [ ] results_three_seeds_before.json, results_three_seeds_after.json,
           baseline_results.json and
           agreement_results.json committed
       [ ] At least four new commits
       [ ] The SAME repository URL as last unit

     Do not delete and recreate this repository.
     ═════════════════════════════════════════════════════════════════════ -->

---

📖 **How to run this project: [RUNNING.md](RUNNING.md)**
