# Personalized Pain and Opioid Craving Dynamics

This repository contains the analysis notebook used for the study of personalized pain and opioid craving dynamics in people receiving medications for opioid use disorder.

Ross, M. K., Stull, S. W., Lambert-Harris, C. A., Marsch, L. A., McLeman, B. M., Campbell, C. I., Does, M. B., Mishra, V., Subramaniam, G., & Frumkin, M. R. *Personalized pain and opioid craving dynamics in people receiving medications for opioid use disorder*. Manuscript under review.

The workflow is implemented in [`analysis.Rmd`](analysis.Rmd). It prepares ecological momentary assessment (EMA) data in R and then fits dynamic structural equation models (DSEM) in Mplus through the `MplusAutomation` package.

## What the analysis does

The notebook performs four main steps:

1. Load EMA data from a CSV file.
2. Reshape and clean the data for Mplus.
3. Fit a group-level DSEM examining lagged relations among pain, pain thoughts, and craving.
4. Fit idiographic DSEM models for individual participants and inspect parameter estimates and convergence diagnostics.

## Models

### Group-level model

The group model estimates two-level DSEM effects for:

- contemporaneous and lagged pain, craving, and pain-thought variables
- autoregressive effects
- residual variances
- within-person covariances

### Idiographic models

The idiographic section runs participant-specific DSEM models for craving only. For each participant, the model includes:

- time effects for day and survey order
- a first-order autoregressive term for craving
- residual variance estimation

## Requirements

The notebook uses R and Mplus.

R packages currently listed in [`requirements.txt`](requirements.txt):

- `psych`
- `ggplot2`
- `tidyr`
- `plyr`
- `dplyr`
- `MplusAutomation`
- `forcats`
- `tableone`

You will also need a working Mplus installation and an environment configured so that MplusAutomation can launch Mplus models.
