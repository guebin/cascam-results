# Parameter Effects

Analysis of how hyperparameters affect CasCAM performance.

---

## Key Parameters

| Parameter | Description | Optimal Range |
|-----------|-------------|---------------|
| `num_iter` | Number of cascading iterations | 10-15 |
| `θ` (theta) | Removal strength | 0.1-0.3 |
| `top_k` | Top-k% threshold | 10-20 |
| `λ` (lambda) | Exponential decay weight | 0.0-0.1 |

---

## Effect of Number of Iterations (`num_iter`)

| num_iter | AP | IoU | Pointing Game | Top-15% |
|----------|-----|-----|---------------|---------|
| 3 | 0.5447 | 0.1661 | 65.02% | 0.5756 |
| 5 | 0.5820 | 0.2090 | 78.82% | 0.5926 |
| 10 | **0.6529** | **0.2366** | **89.24%** | **0.6499** |

*Configuration: θ=0.3, top_k=10, λ=0.1 (Oxford-IIIT Pet)*

**Key Finding**: Performance consistently improves with more iterations. Each iteration refines attention by suppressing previously activated regions.

---

## Effect of θ (Removal Strength)

| θ | Pointing Game (iter=10) | IoU (iter=10) |
|---|-------------------------|---------------|
| 0.1 | 81.33% | 0.2067 |
| 0.3 | **89.24%** | **0.2366** |

*Configuration: top_k=10, λ=0.1 (Oxford-IIIT Pet)*

**Key Finding**: Higher θ produces more aggressive removal, accelerating convergence. θ=0.3 achieves optimal balance.

---

## Effect of Threshold Method

| Method | Description | Pointing Game |
|--------|-------------|---------------|
| Top-k(10) | Top 10% activations | **89.24%** |
| Top-k(20) | Top 20% activations | 78.48% |
| No threshold | Full activation map | 69.01% |

*Configuration: num_iter=10, θ=0.3 (Oxford-IIIT Pet)*

**Key Finding**: Top-k thresholding significantly improves localization by focusing on high-activation regions.

---

## Effect of λ (Exponential Decay)

Weight formula: $w_k = e^{-\lambda k}$ for iteration $k$

| λ | Effect |
|---|--------|
| 0.0 | Uniform weighting (all iterations equal) |
| 0.1 | Slight emphasis on earlier iterations |
| 0.5+ | Strong emphasis on first iterations |

**Key Finding**: λ=0.0 to 0.1 works best. Uniform weighting combines refinements from all iterations effectively.

---

## COCO vs Oxford-IIIT Pet

| Dataset | Best num_iter | Best θ | Best λ |
|---------|---------------|--------|--------|
| Oxford-IIIT Pet | 10 | 0.3 | 0.1 |
| MS-COCO | 15 | 0.1 | 0.0 |

**Key Finding**: More complex datasets (COCO) benefit from more iterations and gentler removal strength.
