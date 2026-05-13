 # Modeling Depression: Extensions, Evaluation, and Individual Recovery

**Aidan Batista — Duke University, Mathematical Modeling Seminar (April 2026)**

This repository contains the Python analysis code and written paper for a mathematical modeling study of major depressive disorder (MDD). Three baseline frameworks from Cochran et al. (2017) are each extended with a new component, then evaluated against two complementary datasets.

## Models

**Markov Chain → Hidden Markov Model**  
A discrete-time Markov chain fits population recovery probabilities from NEMESIS hazard data. The HMM extension replaces hard state thresholds with probabilistic inference via Baum-Welch, assigning each inspection interval a posterior probability of being in a high- or low-recovery phase.

**Gamma AR(1) → Treatment Structural Break**  
A first-order autoregressive model with Gamma-distributed errors is fit to 238 days of individual ESM mood data (Kossakowski et al., 2017), yielding persistence â = 0.30. The treatment extension allows parameters to shift at a known treatment onset, detecting changes in both symptom stickiness and long-run baseline severity.

**Ornstein-Uhlenbeck Random Mood → Kalman Filter**  
The OU model is first fit to NEMESIS population survival data, recovering ⟨T⟩ = 365 days and D = 120 days. The Kalman filter extension moves the model to the individual level, fitting a latent mood trajectory directly to daily ESM observations and recovering a personal relaxation time of T̂ = 7 days.

## Datasets

- **NEMESIS** (van der Werf et al., 2006): population time-to-event data from 250 MDD patients across 18 inspection intervals
- **Kossakowski et al. (2017)**: 238-day ESM record from a single MDD patient, ~1,476 momentary observations aggregated to daily means. Available at [osf.io/j4fg8](https://osf.io/j4fg8)

## Key Finding

The individual relaxation time T̂ = 7 days and population estimate ⟨T⟩ = 365 days differ by a factor of 50. They measure different layers of the same process: daily affect rebounds from momentary lows within a week, while clinical episode resolution takes months. ESM data and population survival data are not interchangeable model inputs.

## Code

Full analysis pipeline in Google Colab:  
[Open notebook](https://colab.research.google.com/drive/1H7v3pUE7ITIL8lV7wcUgVjK1PAlV4dTa?usp=sharing)

## References

- Cochran et al. (2017). *A comparison of mathematical models of mood in bipolar disorder.* Springer.
- van der Werf et al. (2006). *Major depressive episodes and random mood.* Archives of General Psychiatry.
- Kossakowski et al. (2017). *Data from "Critical slowing down as a personalized early warning signal for depression."* Journal of Open Psychology Data.
