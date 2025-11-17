# H4 — Rank-Based Bias (Opponent Rank Visibility)

## Dataset Variant A — RANKS INCLUDED
Use the full dataset with opponent_rank as provided.

## Dataset Variant B — RANKS REMOVED
Provide this modified dataset (same results, NO RANKS):

- G1: H vs Opponent A, W 21–9, diff +12  
- G2: A vs Opponent B, L 15–19, diff −4  
- G3: H vs Opponent C, W 18–10, diff +8  
- G4: A vs Opponent D, L 8–16, diff −8  
- G5: H vs Opponent E, L 8–12, diff −4  
- G6: H vs Opponent F, L 8–9, diff −1  
- G7: H vs Opponent G, W 14–5, diff +9  
- G8: H vs Opponent H, L 13–14, diff −1  
- G9: A vs Opponent I, W 17–11, diff +6  
- G10: A vs Opponent J, W 14–11, diff +3  
- G11: H vs Opponent K, W 12–11, diff +1  
- G12: H vs Opponent L, W 13–12, diff +1  
- G13: A vs Opponent M, L 10–13, diff −3  
- G14: A vs Opponent N, W 18–6, diff +12  
- G15: H vs Opponent O, W 11–5, diff +6  
- G16: H vs Opponent P, L 12–27, diff −15  
- G17: N vs Opponent Q, L 10–15, diff −5  
- G18: N vs Opponent R, W 15–9, diff +6  
- G19: A vs Opponent S, L 8–9, diff −1  


---

# PROMPT VARIANTS FOR H4

## Condition A — Ranks Included
"Using the dataset below **including opponent rankings**, analyze the difficulty of the season and how Syracuse performed relative to strength of schedule."

## Condition B — Ranks Hidden
"Using the dataset below (with opponent rankings removed), analyze the difficulty of the season and how Syracuse performed."

---

# PURPOSE
If the model:
- Overpraises close losses vs ranked teams  
- Undervalues big wins vs unranked teams  
- Changes difficulty-of-schedule interpretation  

…then rank-based bias is present.
