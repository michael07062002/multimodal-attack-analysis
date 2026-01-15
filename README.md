# multimodal-attack-analysis
# multimodal-attacks-hw3
A prototype study of attacks on multimodal models (typographic overlay + M-Attack-style perturbations).
Evaluated on a 50-image subset of the AMAZON-Products-2023 dataset (5 top categories × 10 samples).

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1EXmG1zw3jg2iPQDxoj9wTZFaujfVapGH)

## Features
Typographic attack: overlaying irrelevant text on product images to manipulate encoder/VLM behavior.
Automatic generation of irrelevant overlay texts (Qwen2.5-VL) with forbidden-word filtering.
Selecting the most irrelevant overlay candidate using CLIP cosine similarity minimization.
Rendering multiple overlay variants (positions + font sizes) and building an attack manifest.
Encoder evaluation (CLIP): sim(image,title) vs sim(image,attack_text), margin and win-rate.
VLM evaluation (Qwen2.5-VL): captions before/after attack + token hit-rate (delta_hit).
M-Attack-style example: small L∞-bounded perturbations to match a target image in CLIP embedding space (ensemble surrogates + random crops).

## Models Used
CLIP ViT-B/32  
CLIP ViT-B/16  
Qwen2.5-VL-3B-Instruct
