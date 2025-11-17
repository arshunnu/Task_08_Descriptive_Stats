# REPORT.md — LLM Bias Evaluation Report

## Phase 4: Report & Mitigation

This report presents the executive summary, methodology, results, bias catalogue, mitigation strategies, and limitations for the Syracuse Women’s Lacrosse LLM bias experiment.

---

# 1. Executive Summary

This project evaluated how large language models (GPT-4, Claude 3 Opus, Gemini 1.5 Pro) respond to differently framed prompts when summarizing the 2025 Syracuse Women’s Lacrosse season. Using 81 responses across four hypotheses—positive vs negative framing, neutral framing, hypothesis-driven framing, and rank-based visibility—the goal was to measure how strongly prompt structure affects LLM interpretation.

The findings demonstrate clear and systematic framing bias across all models. Positive prompts consistently generated optimistic narratives emphasizing growth, momentum, and resilience. Negative prompts produced pessimistic summaries that focused on inconsistency, defensive issues, and pressure breakdowns. Neutral prompts were closest to the dataset but still included mild interpretive statements. Rank-based prompts changed tone depending on whether opponent rankings were shown or hidden.

Quantitative analysis revealed strong sentiment separation: positive prompts had the highest sentiment averages, negative prompts the lowest, and neutrals near zero. Qualitatively, models exhibited cherry-picking behaviors: positive prompts highlighted high-margin wins (e.g., +12, +12, +6), while negative prompts emphasized heavy losses (−15, −8, −5). All models avoided factual errors—no invented games, players, or incorrect scores—but frequently introduced narrative and causal fabrications, such as psychological explanations or inferred momentum shifts.

Overall, the results show that LLMs are highly sensitive to prompt framing and often extend beyond the provided statistics to construct coherent narratives. These behaviors emphasize the importance of grounding instructions, structured outputs, and bias mitigation methods when using LLMs for evaluative or analytical tasks.

---

# 2. Methodology

## 2.1 Experimental Design
A repeated-measures experimental setup was used with four hypotheses:

- **H1:** Positive vs negative framing  
- **H2:** Neutral framing  
- **H3:** Positive vs negative hypothesis embedding  
- **H4:** Rank visibility vs rank removal  

All prompts included the full statistical dataset from the 2025 Syracuse Women’s Lacrosse season.

## 2.2 Models Evaluated
- GPT-4  
- Claude 3 Opus  
- Gemini 1.5 Pro  

Each model was queried three times per prompt, producing 81 responses total.

## 2.3 Prompt Templates
All prompt variants are stored in the `prompts/` directory.  
Each template includes:

- Full embedded dataset  
- Controlled framing variation  
- Consistent structure across hypotheses  

## 2.4 Analysis Approach

- Sentiment scoring (positive vs negative lexicon)  
- Keyword frequency analysis (team / defense / offense)  
- Cherry-picking detection (which games were referenced)  
- Fabrication scoring (narrative, causal, trend-based fabrications)  
- Model-style comparison (GPT vs Claude vs Gemini behavioral differences)

All analysis files are under the `analysis/` directory.

---

# 3. Results

## 3.1 Quantitative Findings

- Positive prompts → highest sentiment  
- Negative prompts → lowest sentiment  
- Neutral prompts → near zero  
- Rank visibility → slightly more negative interpretation  
- Rank removed → more neutral or slightly positive  

## 3.2 Qualitative Findings

**Positive Prompts (H1+, H3+):**  
- Highlight G1 (+12), G14 (+12), G18 (+6)  
- Emphasize resilience, cohesion, improvement  

**Negative Prompts (H1–, H3–):**  
- Highlight G16 (−15), G4 (−8), G17 (−5)  
- Focus on inconsistency, breakdowns, defensive gaps  

**Neutral Prompts (H1N, H2, H3N):**  
- Balanced but still interpretive in some phrasing  

**Rank-Based Prompts (H4):**  
- Ranks shown → emphasis on difficulty, tough schedule  
- Ranks hidden → tone shifts more moderate  

## 3.3 Model Behavior Differences

- **GPT-4:** Most analytical and structured  
- **Claude:** Most reflective, narrative-heavy  
- **Gemini:** Most concise and literal  

---

# 4. Bias Catalogue

| **Bias Type**               | **Description**                                         | **Severity** |
|-----------------------------|---------------------------------------------------------|--------------|
| **Framing Bias**            | Narrative shifts based on positive/negative wording     | **High**     |
| **Cherry-Picking Bias**     | Selective use of wins/losses to match framing          | **High**     |
| **Narrative Fabrication**   | Causal or psychological claims without evidence        | **Medium**   |
| **Strength-of-Schedule Bias** | Rank visibility changes tone and interpretation      | **Medium**   |
| **Model-Style Bias**        | Differences due to model personality/tone               | **Low**      |

---

# 5. Mitigation Strategies

## 5.1 Prompt-Level Mitigations
- Use strict grounding instructions (“Only use provided statistics”).  
- Avoid positive/negative emotional wording.  
- Use controlled formats (tables, bullet points).  

## 5.2 Model-Level Mitigations
- Require evidence citations for every claim.  
- Use cross-model consensus filtering.  
- Penalize unsupported inferences during evaluation.  

## 5.3 Post-Processing Mitigations
- Automatic detection of fabricated narrative language.  
- Rule-based filtering for unsupported claims.  
- Restrict outputs to factual descriptions only.  

---

# 6. Limitations

- Dataset is team-level only; individual-player bias not measurable.  
- Narrative summarization encourages interpretation by nature.  
- Sentiment analysis may miss subtle linguistic drift.  
- Temperature randomness introduces variation between runs.  
- Only three models were tested; results may not generalize universally.  
- Long-term narrative drift was not tested due to short outputs.  

---

# End of Report
