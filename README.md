# CasCAM Supplementary Materials

Supplementary materials for **CasCAM: Cascaded Class Activation Mapping**.

## View Online

**[https://guebin.github.io/cascam-results/](https://guebin.github.io/cascam-results/)**

## Contents

| Tab | Description |
|-----|-------------|
| Comparison Figures | Visual comparison of CAM outputs (interactive gallery) |
| Performance Metrics | Quantitative comparison with baseline CAM methods on Oxford-IIIT Pet and MS-COCO datasets |

## Quick Summary

CasCAM achieves state-of-the-art performance on object localization metrics:

| Metric | CasCAM | Best Baseline | Improvement |
|--------|--------|---------------|-------------|
| **Pointing Game** | 89.24% | 59.61% (FullGrad) | +49.7% |
| **IoU** | 30.49% | 23.50% (FullGrad) | +29.7% |
| **AP** | 0.6529 | 0.5243 (ScoreCAM) | +24.5% |
| **Top-15% Energy** | 64.99% | 51.69% (ScoreCAM) | +25.7% |

*Results on Oxford-IIIT Pet dataset with best configuration (num_iter=10, theta=0.3, top_k=10, lambda=0.1).*
