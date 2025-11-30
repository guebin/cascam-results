# Comparison Figures

Visual comparison of CAM outputs across methods and iterations.

---

## Iterative Refinement Process

The following visualizations show how CasCAM progressively refines attention maps through cascading iterations.

### Removed Images Visualization

Each iteration produces "removed images" where high-activation regions are suppressed:

| Iteration | Effect |
|-----------|--------|
| 1-3 | Remove obvious background artifacts |
| 4-6 | Refine object boundaries |
| 7-10 | Fine-tune focus on discriminative features |

---

## CAM Method Comparison

### Oxford-IIIT Pet Dataset

| Method | Characteristic |
|--------|----------------|
| **CasCAM** | Precise object localization, minimal background activation |
| CAM/GradCAM | Broad activation, often includes background |
| FullGrad | Good coverage but includes irrelevant regions |
| ScoreCAM | Reasonable localization but slower |

### MS-COCO Dataset

| Method | Characteristic |
|--------|----------------|
| **CasCAM** | Focuses on primary object despite clutter |
| CAM/GradCAM | Scattered activation across multiple regions |
| FullGrad | Better than CAM but still includes distractors |

---

## λ Effect Visualization

Different λ values produce different CAM combinations:

| λ | Visual Effect |
|---|---------------|
| 0.0 | Broader attention (uniform weighting) |
| 0.1 | Balanced focus |
| 0.5 | Sharper, focused attention (early iteration emphasis) |

---

## Figures (To Be Added)

- [ ] `removed_images_oxford.pdf` - Iterative removal visualization
- [ ] `cam_comparison_oxford.pdf` - Method comparison on Oxford
- [ ] `cam_comparison_coco.pdf` - Method comparison on COCO
- [ ] `lambda_effect.pdf` - λ parameter visualization
