# Detecting Fish Hunger Levels by Monitoring and Classifying Their Underwater Swimming Patterns

A low-cost, camera-based system that estimates how hungry farmed fish are by reading their swimming behavior — so farmers can feed based on actual need instead of a fixed clock.

Submitted to **Research Expo 2.0: Inter University Research Proposal & Datathon 2026**, hosted by the Research & Publication Unit, Department of CSE, University of Asia Pacific.

**Team**
- Minhaz Uddin
- Ishmam Mohammed Chowdhury
- Syed Ar Rafi

Department of Computer Science and Engineering (CSE), BRAC University

---

## The Pitch

Feed is the single biggest cost in fish farming — often around 60% of total production cost in Bangladeshi aquaculture. Most farmers still feed on a fixed schedule or by eyeballing the pond, which leads to a lot of overfeeding. Overfed ponds waste money and pollute the water; underfed fish grow slower.

Fish actually change how they swim when they're hungry — how fast they move, how often they turn, where they sit in the water column, how tightly they school. Our idea is to point an underwater camera at the pond, track that behavior, and use a machine learning model to classify hunger level as **Low, Moderate, or High** — giving farmers a simple, real-time signal for whether it's actually time to feed.

This repo holds the full proposal, our poster, and an early proof-of-concept notebook.

## Table of Contents
- [Problem Statement](#problem-statement)
- [Research Objectives](#research-objectives)
- [Research Questions & Contribution](#research-questions--contribution)
- [Proposed Methodology](#proposed-methodology)
- [Expected Outcomes](#expected-outcomes)
- [Repo Structure](#repo-structure)
- [References](#references)
- [Contact](#contact)

## Problem Statement

- **Inaccurate feeding methods** — fixed-time feeding doesn't check whether fish are actually hungry, so overfeeding is common.
- **Wasted money** — excess feed that goes uneaten sits in the pond, which is a direct financial loss and hurts water quality.
- **High-cost tech is out of reach** — existing smart-feeding systems are built for large, well-funded operations, not small and mid-sized ponds.
- **No local tools or data exist** — there's no simple, low-cost way to estimate hunger for locally farmed species, and no public dataset to build one from.

## Research Objectives

1. Build a low-cost, camera-based setup to record underwater fish behavior.
2. Track fish and extract behavioral features — swimming speed, turning frequency, vertical position, and schooling density.
3. Train a model (LSTM or CNN-LSTM) to classify hunger as Low, Moderate, or High.
4. Compare need-based feeding against fixed-schedule feeding to see whether it actually helps.

## Research Questions & Contribution

**RQ1.** Can underwater swimming patterns reliably show how hungry a fish is?
**RQ2.** Can a low-cost, camera-only system help farmers decide when to feed?

**What this project contributes:**
- A labeled dataset linking swimming behavior to hunger state for locally farmed fish — something that doesn't really exist yet.
- A simple, real-time hunger indicator designed for small farms, not industrial ones.
- A clearer picture of which behavioral cue (speed, turning, depth, or schooling) is the strongest signal of hunger.

## Proposed Methodology

1. **Record** — film fish underwater at different times since their last feeding, so we have a known hunger label for each clip.
2. **Track** — detect the fish and follow their paths frame by frame.
3. **Extract features** — speed, turning, vertical position, schooling density.
4. **Train** — feed those features into an LSTM / CNN-LSTM model to classify Low, Moderate, or High hunger.
5. **Test** — run the model on new video it hasn't seen, and compare need-based vs. fixed-schedule feeding on feed used, growth, and water quality.

```
Underwater Video → Detection & Tracking → Feature Extraction
→ LSTM / CNN-LSTM → Hunger Level (Low / Moderate / High)
→ Feeding Decision Support
```

See `/poster/` for the full visual breakdown of this pipeline.

## Expected Outcomes

- A working prototype that classifies hunger level from underwater video.
- A labeled behavioral dataset for locally farmed fish species.
- A ranking of which movement feature is the strongest predictor of hunger.
- Evidence on whether need-based feeding actually reduces wasted feed and helps water quality.

## Repo Structure

```
.
├── README.md
├── poster/
│   └── poster.png / poster.pdf        # the printed poster
├── docs/
│   └── proposal.pdf                   # full written proposal
├── notebooks/
│   └── proof_of_concept.ipynb         # synthetic-data demo of the feature + classification pipeline
└── references.md
```

## References

1. Fagun, I. A., Rishan, S. T., Shipra, N. T., & Kunda, M. (2020). Present Status of Aquaculture and Socio-Economic Condition of Fish Farmers in a Rural Setting in Bangladesh. *Research in Agriculture, Livestock and Fisheries*, 7(2), 329–339.
2. Hossain, M. A. et al. (2025). Evaluating Feeding Strategies to Improve Growth and Profitability in Carp Fattening. *Aquaculture and Fisheries* (in press).
3. Måløy, H., Aamodt, A., & Misimi, E. (2019). A Spatio-Temporal Recurrent Network for Salmon Feeding Action Recognition from Underwater Videos in Aquaculture. *Computers and Electronics in Agriculture*, 167, 105087.
4. Zhou, C., Xu, D., & Wang, Y. (2019). Evaluation of Fish Feeding Intensity in Aquaculture Using a Convolutional Neural Network and Machine Vision. *Aquaculture*, 507, 457–465.

Full list with links in [`references.md`](./references.md).

## Contact

Questions about the proposal? Reach out to the team — Minhaz Uddin, Ishmam Mohammed Chowdhury, or Syed Ar Rafi, Department of CSE, BRAC University.

---

*This repository documents a research proposal submitted to Research Expo 2.0 (2026). The system described is a proposed design, not a completed product — prototype code and results will be added here as the work progresses.*
