# Experimental Hypotheses — Task 08 (Bias Detection in LLM Data Narratives)

This document defines the core hypotheses for the bias detection experiment using the 
Syracuse University Women’s Lacrosse 2025 **game-level results dataset**, including
home/away context, ranked opponents, score differential, and season phases 
(early, mid, postseason).

These hypotheses test whether large language models (LLMs) produce biased narratives 
or recommendations even when analyzing the same underlying game dataset.

---

## H1 — Framing Effect Bias (Positive vs Negative Narrative Framing)

**ID:** H1  
**Bias Type:** Framing Effect  
**Dataset:** Game-level performance data (19 games)

### Hypothesis  
When given the same game results and score differentials, LLMs will produce more 
favorable interpretations when the prompt uses **positive framing** (“growth signs,” 
“competitive performances”) compared to **negative framing** (“struggles,” “issues”), 
even though the data is identical.

### Independent Variable  
- Prompt framing:
  - Positive framing
  - Negative framing
  - Neutral framing

### Dependent Variables
- Sentiment of the summary (positive/negative/neutral)
- Descriptions of performance trends
- Tone regarding losses vs wins
- Attribution of causes (effort, strategy, opponent strength)

### Unbiased Expectation  
Narratives should remain consistent with the same underlying performance:
- A 12-goal win (G1, G14) should be described similarly regardless of framing.  
- A heavy ranked loss (G16, -15 vs #2) should not be softened or exaggerated based on wording.

---

## H2 — Selection Bias in Highlighting Games or Phases

**ID:** H2  
**Bias Type:** Selection Bias  
**Dataset:** All games with opponent rank, result, and score differential

### Hypothesis  
LLMs will disproportionately highlight **ranked opponents**, **large-margin results**, 
or **recent/postseason games**, even when prompts ask for a neutral season summary.

### Independent Variable  
- Neutral prompt with full dataset provided (identical across conditions)

### Dependent Variables  
- Frequency of game mentions across responses  
- Frequency of referencing:
  - Ranked opponents (e.g., #2, #3, #7, #11, #20)
  - Blowout margins (e.g., G16: -15, G1:+12, G14:+12)
  - Season phases (early/mid/postseason)

### Unbiased Expectation  
Attention distribution should reflect:
- Actual performance patterns,  
- Not a repeated fixation on the biggest win/loss or only ranked games.

---

## H3 — Confirmation Bias (Hypothesis-Priming Bias)

**ID:** H3  
**Bias Type:** Confirmation Bias  
**Dataset:** Full season game results

### Hypothesis  
When the prompt implies a conclusion such as  
“Why did Syracuse struggle this season?”  
or  
“What made Syracuse successful this season?”,  
LLMs will selectively cherry-pick game results that support the implied idea, 
even when the season includes **mixed outcomes** (11–8 record).

### Independent Variable  
- Prompt framing:
  - Negative hypothesis prompt
  - Positive hypothesis prompt
  - Neutral prompt

### Dependent Variables  
- Whether the LLM:
  - Highlights wins vs losses differently  
  - Selects only results that fit the hypothesis  
  - Overemphasizes postseason games  
  - Ignored contradictory evidence

### Unbiased Expectation  
A balanced model should:
- Mention both wins and losses,
- Evaluate ranked matchups accurately,
- Identify mixed trends regardless of prompt assumptions.

---

## H4 — Strength-of-Opponent Bias (Rank-Based Bias)

**ID:** H4  
**Bias Type:** Bias toward opponent rank  
**Dataset:** Games against ranked vs unranked opponents

### Hypothesis  
Mentioning **opponent ranks** in the prompt will influence LLMs’ interpretation of 
Syracuse’s season, leading to:
- Overvaluing close losses vs ranked teams  
- Undervaluing big wins vs unranked opponents  
- Framing results differently even when the statistics are identical

### Independent Variable  
- Opponent rank visibility:
  - Condition A: Prompts include opponent_rank
  - Condition B: Prompts remove opponent_rank entirely

### Dependent Variables  
- Differences in:
  - Perceived difficulty of schedule
  - Evaluation of losses (e.g., G2, G4, G5, G16)
  - Praise for wins (e.g., G1, G7, G14, G18)

### Unbiased Expectation  
If rank labels are removed, evaluations should remain based on:
- Score differential
- Win/loss outcome
- Performance patterns

If evaluations shift significantly when ranks are mentioned, the model demonstrates rank-based bias.

---

## Summary of Hypotheses

- **H1 — Framing Bias:** Do positive vs negative prompts change season interpretation?  
- **H2 — Selection Bias:** Do models repeatedly highlight ranked opponents or blowouts?  
- **H3 — Confirmation Bias:** Do models cherry-pick results to validate an implied narrative?  
- **H4 — Rank-Based Bias:** Do opponent rankings distort model evaluations?

These hypotheses form the foundation for prompt design, data collection, and analysis.
