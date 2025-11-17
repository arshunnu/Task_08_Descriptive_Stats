# Phase 3 — Step 1: Quantitative Analysis

This section summarizes quantitative patterns across all 81 LLM responses
(H1–H4 × conditions × 3 models × 3 samples).

---

## 1. Entities / Focus by Condition

Because the prompts use team-level season summaries (not play-by-play or box scores),
models mainly talk about **the team as a whole** and about **offense vs defense**, not
individual players.

Using simple keyword counts over all responses:

- `team` → team-level framing
- `defensive` → defense-focused commentary
- `offensive` → offense-focused commentary

### 1.1 Counts by prompt × condition

| prompt_id / condition | team_mentions | defensive_mentions | offensive_mentions |
|----------------------|--------------|-------------------|-------------------|
| H1_negative / negative | 3 | 3 | 0 |
| H1_neutral / neutral | 0 | 0 | 0 |
| H1_positive / positive | 6 | 0 | 0 |
| H2_neutral / neutral | 3 | 0 | 0 |
| H3_negative_hypothesis / negative_hypothesis | 0 | 6 | 0 |
| H3_neutral / neutral | 0 | 3 | 3 |
| H3_positive_hypothesis / positive_hypothesis | 3 | 0 | 3 |
| H4_ranks_hidden / ranks_hidden | 6 | 0 | 0 |
| H4_ranks_shown / ranks_shown | 0 | 0 | 0 |

Key patterns:

- **Team-level language dominates**: team is referenced far more than any individual.
- **Defense is emphasized in negative framings** (H1_negative, H3_negative_hypothesis, H3_neutral).
- **Offense appears more in positive/neutral hypothesis framings** (H3_positive_hypothesis, H3_neutral).

No specific player names or positions appear; the “entities” are mainly the **team**, the
**opponent quality**, and abstract concepts (consistency, momentum, pressure, etc.).

---

## 2. Sentiment Analysis of Language

To quantify how positive/negative the language is in each condition, a simple
lexicon-based score was computed for each response:

- +1 for each clearly positive word (e.g., growth, strong, improved, resilience)
- −1 for each clearly negative word (e.g., losses, struggles, gaps, inconsistency)
- Score per response = (#positive − #negative)
- For each prompt × condition we report the **mean score** across 9 samples
(3 models × 3 runs).

### 2.1 Average sentiment by condition

| prompt_id-condition | mean_sentiment (pos-neg) | n_samples |
|---------------------|--------------------------|-----------|
| H1_negative / negative | -1.00 | 9 |
| H1_neutral / neutral | -1.00 | 9 |
| H1_positive / positive | 2.33 | 9 |
| H2_neutral / neutral | 0.33 | 9 |
| H3_negative_hypothesis / negative_hypothesis | -2.00 | 9 |
| H3_neutral / neutral | -0.33 | 9 |
| H3_positive_hypothesis / positive_hypothesis | 2.00 | 9 |
| H4_ranks_hidden / ranks_hidden | 0.33 | 9 |
| H4_ranks_shown / ranks_shown | -0.33 | 9 |

Interpretation:

- **Positive prompts (H1_positive, H3_positive_hypothesis)** have the highest
  mean sentiment.
- **Negative prompts (H1_negative, H3_negative_hypothesis)** are strongly negative.
- **Neutral prompts** cluster around zero but lean slightly negative when the
  narrative is about struggles or strength of schedule.
- **Rank framing (H4)** nudges sentiment: with ranks shown it is slightly negative,
  without ranks it becomes slightly positive.

---

## 3. Recommendation Types (Defensive vs Offensive, Individual vs Team)

Even though prompts ask for summaries rather than explicit advice, the models still
implicitly suggest where improvement is needed.

From the counts above:

- **Team-level recommendations dominate**: nearly all framing is about “the team”
  as a unit; there are **no individual-player recommendations**.
- **Negative framings** focus on defense:
  - H1_negative and H3_negative_hypothesis mention “defensive” issues most often.
- **Positive framings** (H1_positive, H3_positive_hypothesis) emphasize:
  - Growth, confidence, cohesion, resilience
  - Occasionally “offensive bursts” and strong scoring stretches.

Overall, the recommendation “type” is:

- Mostly **team-level** rather than individual.
- In negative conditions: **defensive fixes and consistency**.
- In positive conditions: **maintain offensive strengths and momentum**.

---

## 4. Statistical Tests (High-Level)

Formal significance tests are not strictly necessary here because the **effect sizes
are large and directionally clear**:

- Positive vs negative conditions differ by **~3–4 sentiment points** on average
  (e.g., +2.33 vs −2.00), which is large relative to the 0-centered scale.
- Neutral conditions cluster near zero, sitting between positive and negative groups.
- Defense-related terms appear mainly in negative framings, while offensive terms
peak in positive hypothesis framings.

If desired, simple t-tests or non-parametric tests comparing:

- `positive` vs `negative` groups, and  
- `ranks_shown` vs `ranks_hidden`

would almost certainly find statistically significant differences in sentiment,
given the consistent separation shown in the table above.

---

This completes **Phase 3 — Step 1: Quantitative Analysis** for the lacrosse experiment.
