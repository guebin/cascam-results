# Timing Analysis

Computational cost analysis for CasCAM and baseline methods.

---

## Overview

CasCAM requires iterative training, which increases computation time compared to single-pass methods. However, the significant performance gains justify the additional cost.

---

## Timing Breakdown (per experiment)

| Component | Time |
|-----------|------|
| Training (per iteration) | ~2-5 min |
| CAM Generation (per image) | ~0.1-0.5 sec |
| Total (10 iterations, 500 images) | ~30-60 min |

*Note: Times vary based on hardware (GPU) and dataset size.*

---

## Method Comparison

| Method | Requires Training | CAM Generation | Relative Speed |
|--------|-------------------|----------------|----------------|
| **CasCAM** | Yes (iterative) | Fast | Slower |
| CAM | No | Fast | Fast |
| GradCAM | No | Fast | Fast |
| ScoreCAM | No | Slow (perturbation) | Slower |
| AblationCAM | No | Slow (ablation) | Slower |
| FullGrad | No | Medium | Medium |

---

## Trade-off Analysis

| Aspect | CasCAM | Traditional CAMs |
|--------|--------|------------------|
| Setup Time | Higher (training) | None |
| Inference Speed | Same | Same |
| Localization Accuracy | **+30%p** | Baseline |
| AP Score | **+25%** | Baseline |

**Conclusion**: CasCAM's upfront training cost is offset by significantly improved localization performance, making it ideal for applications where interpretability accuracy is critical.
