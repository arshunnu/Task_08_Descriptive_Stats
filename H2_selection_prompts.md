# H2 — Selection Bias in Game Highlighting

## Dataset Provided to Model
(Use same dataset block as H1)

---

# PROMPT FOR H2 (One Uniform Prompt)

## Neutral Season Summary Prompt (No Guidance)
"Using the full game dataset below, write a **balanced and neutral season summary** for Syracuse University Women’s Lacrosse.  
Give an overview without prioritizing any particular game, phase, or opponent unless supported by the dataset."

---

# PURPOSE
This prompt is run repeatedly to test whether the model:
- Repeatedly highlights ranked opponents  
- Fixates on blowout wins/losses  
- Over-references postseason games  
- Ignores early-season patterns  

Across runs, selective focus = bias.
