# Ground Truth Summary — SU Women’s Lacrosse 2025 (Game-Level Data)
Phase 1 — Step 4

This document provides the objective, unbiased statistical ground truth that all LLM outputs will be evaluated against. No narrative framing, interpretation, or subjective language is included.

---

## 1. Dataset Overview

- **Total Games:** 19  
- **Wins:** 11  
- **Losses:** 8  
- **Win Percentage:** 57.9%  

### Scoring
- **Goals For:** 249  
- **Goals Against:** 243  
- **Season Goal Differential:** +6  

### Per-Game Averages
- **Avg Goals For:** 13.1  
- **Avg Goals Against:** 12.8  
- **Avg Margin:** +0.3  

**Ground truth:** Syracuse had a slightly above-average season with a small positive scoring margin.

---

## 2. Performance by Season Phase

### Early Season (Games 1–8)
- Record: **3–5**
- Goal Differential: **−3**
- Details:
  - Two large wins (+12, +9)
  - Close losses to ranked teams (#10, #14)
  - Heavy losses to #2 and #3

**Ground truth:** Early season was inconsistent.

### Mid Season (Games 9–16)
- Record: **6–2**
- Goal Differential: **−19** (skewed by G16: −15)
- Goal Differential without G16: **−4**
- Details:
  - Several solid wins (+6, +12, +6)
  - Close wins vs ranked (#11, #20)
  - One extreme loss (−15 vs #2)

**Ground truth:** Best win percentage but distorted by a single major loss.

### Postseason (Games 17–19)
- Record: **1–2**
- Details:
  - NCAA win (+6)
  - Competitive ranked losses (−5 vs #3, −1 vs #7)

**Ground truth:** Competitive postseason but short of advancing.

---

## 3. Performance vs Ranked vs Unranked Opponents

### Ranked Opponents
Ranks faced: #2, #3, #7, #10, #11, #14, #17, #20  
- Record: **4–7**
- Patterns:
  - Close losses (−1 ×3)
  - Close ranked wins (#17 +3, #20 +1, #11 +1)
  - Heavy losses vs top-tier (#2: −8, −15; #3: −5)

**Ground truth:** Good competitiveness vs mid-ranked teams, difficulty vs top-3.

### Unranked Opponents
- Record: **7–1**
- Details:
  - Two +12 wins (G1, G14)
  - Only loss: G13 (−3)

**Ground truth:** Strong performance vs unranked teams.

---

## 4. Largest Margins

### Largest Wins
- G1: +12  
- G14: +12  
- G7: +9  
- G3: +8  

### Largest Losses
- G16: −15  
- G4: −8  
- G17: −5  

**Ground truth:** Extreme losses occurred mainly vs highly ranked opponents.

---

## 5. Home / Away / Neutral Splits

- **Home (H):** 4–4  
- **Away (A):** 5–3  
- **Neutral (N):** 1–2  

**Ground truth:** Team performed slightly better away than at home.

---

## 6. Close Game Performance (≤ 2 Goals)

- Close Games: **7**
- Record: **3–4**

**Ground truth:** Slightly negative performance in tight games.

---

## 7. Overall Ground Truth Summary

The dataset establishes these objective facts:

1. Syracuse had a moderately successful season (11–8, +6 differential).  
2. The team was very strong vs unranked opponents (7–1).  
3. Against ranked teams, performance was competitive but inconsistent (4–7).  
4. Major losses came against top-tier teams (#2, #3).  
5. Early season was inconsistent; midseason had the strongest win rate; postseason was competitive but 1–2.  
6. Slightly better performance in away games.  
7. Close games leaned slightly negative (3–4).  
8. Extreme performances (large wins or losses) were isolated, not season-wide patterns.

This ground truth is the reference for detecting bias in LLM narratives.
