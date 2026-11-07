\# From Words to Worlds: Text-to-Image Generation with Latent Diffusion



IE 7615 Deep Learning for AI — Generative Project (Group 10)



\## Overview

A text-to-image pipeline built on a \*\*pretrained\*\* latent diffusion

model conditioned on CLIP text embeddings. We treat generation as a

controlled inference problem and study how sampling and conditioning

choices affect image fidelity and prompt alignment — no training from

scratch.



\## Team

| Member | Role |

|---|---|

| Sathya Sai Rajan | Dataset curation, dedup, reproducibility logging |

| Kush Pulindra Patel | Pipeline \& text-conditioning integration |

| Varun Ponugoti | Experimentation, repository owner |

| Vignesh R. Nambiar | Evaluation (FID/IS/CLIPScore), ethical analysis |



\## Model \& Dataset

\- \*\*Base model:\*\* `stable-diffusion-v1-5/stable-diffusion-v1-5`

&#x20; (fallback: `sd-legacy/stable-diffusion-v1-5`)

\- \*\*Text encoder:\*\* CLIP ViT-L/14 (SD 1.5); OpenCLIP ViT-H/14 (SD 2.1, for comparison)

\- \*\*Dataset:\*\* curated COCO Captions 2017 subset (\~2,000 image–caption pairs)



\## Experiments

\- Classifier-free guidance scale sweep (fidelity vs. diversity)

\- Sampler/step comparison: DDIM, PNDM, DPM-Solver

\- Backbone comparison: SD 1.5 vs. SD 2.1 (text-encoder effect)

\- Metrics: FID, Inception Score, CLIPScore + qualitative gallery



\## Setup

&#x20;   git clone https://github.com/sathyaa23/text-to-image-diffusion.git

&#x20;   cd text-to-image-diffusion

&#x20;   pip install -r requirements.txt



Model weights (\~4 GB) download automatically on first run. Both

mirrors are public — no Hugging Face token needed. A CUDA GPU is

recommended (tested on a Colab T4).



\## Reproducibility

All runs use a fixed seed (42). `outputs/<milestone>/run\_log.json`

records model ID, scheduler, step count, guidance scale, and pinned

library versions for every generated image.



\## Milestones

\- \*\*M1 — Setup \& Dataset:\*\* proposal, 5 baseline runs, repo init

\- \*\*M2 — Integration \& Baseline:\*\* conditional generation, guidance/noise tuning

\- \*\*M3 — Evaluation \& Analysis:\*\* FID/IS, prompt-alignment, sensitivity study

\- \*\*M4 — Final Report \& Presentation:\*\* 6–8 page report, gallery, demo

