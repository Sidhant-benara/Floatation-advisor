# Flotation Advisor: Phase 1 prototype

**Live demo:** https://sidhant-benara.github.io/Floatation-advisor/

A decision-support tool for **iron ore flotation**, built as part of my final-year project at IIT (ISM) Dhanbad,
*ML & AI-Based Process Automation in Mineral Processing for Iron Ore Beneficiation* (Department of Mineral &
Metallurgical Engineering).

It turns past laboratory flotation tests into three things an operator or engineer can use:

- **Predict:** for a chosen setting, it predicts concentrate grade (Fe, Al₂O₃, SiO₂), recovery and yield, each with its typical error.
- **Recommend:** for a grade target, it searches the tested range and returns the setting with the best recovery (or yield) that meets it.
- **Flag:** rule-based warnings that say what is off, why, and what to check when a setting is likely to cost grade or yield.

## Data

- 48 measured laboratory flotation tests, supplied by the project guide (`DATA_FOR_MODELING.xlsx`)
- A complete grid of settings: every combination of the tested levels was run once
- **4 inputs:** pulp density, pH, collector dosage, frother dosage
- **5 outputs:** Fe, Al₂O₃ and SiO₂ in the concentrate, plus recovery and yield

## Model

- A simple straight-line (linear) model is fitted first and has to beat the average.
- Five other methods were tested against it, using validation that holds data back (leave one test out, and leave one pH level out).
- Recovery and yield are modelled separately, because lab balances rarely close exactly.

## Ground rules and limits

- Predictions are valid **only inside the tested range**. The sliders stop at the tested limits.
- Collector and frother were tested at two levels, so values between them assume a straight-line change.
- Flotation time, air, impeller speed, reagent types and feed are held fixed and not modelled.
- Not claimed: plant-scale accuracy, other ores, other circuits.

## Roadmap (to April 2027)

| Month | Milestone |
|---|---|
| Nov 2026 | Core engine: streams, cells, circuit, mass balance, flowsheet drawing |
| Jan 2027 | Validated predictor, with a validation report against baselines |
| Feb 2027 | Recommender and flagger, with rules reviewed by the guide |
| Mar 2027 | Final interface and case study on this ore |
| Apr 2027 | Thesis, user guide, code repository and live demonstration |

The next phase puts this cell model inside a rougher–scavenger–cleaner circuit with a full mass balance.

## How to run

Open the live demo link above, or download `index.html` and open it in any browser. No installation needed.

---

Sidhant Veer Benara · B.Tech, Mineral & Metallurgical Engineering, IIT (ISM) Dhanbad ·
[LinkedIn](https://www.linkedin.com/in/sidhant-veer-benara-474a5427b/)
