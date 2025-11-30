# CasCAM Results

Comprehensive experimental results for **CasCAM: Cascade Class Activation Mapping**.

## 📊 Navigation

| Section | Description |
|---------|-------------|
| [1. Performance Metrics](docs/performance_metrics.md) | Quantitative comparison with baseline CAM methods |
| [2. Parameter Effects](docs/parameter_effects.md) | Ablation study on hyperparameters |
| [3. Timing Analysis](docs/timing_analysis.md) | Computational cost analysis |
| [4. Comparison Figures](docs/comparison_figures.md) | Visual comparison of CAM outputs |

---

## Quick Summary

CasCAM achieves state-of-the-art performance on object localization metrics:

| Metric | CasCAM | Best Baseline | Improvement |
|--------|--------|---------------|-------------|
| **Pointing Game** | 89.24% | 59.61% (FullGrad) | +49.7%p |
| **IoU** | 30.49% | 23.50% (FullGrad) | +29.7% |
| **AP** | 0.6529 | 0.5243 (ScoreCAM) | +24.5% |
| **Top-15% Energy** | 64.99% | 51.69% (ScoreCAM) | +25.7% |

*Results on Oxford-IIIT Pet dataset with ResNet-50 backbone.*

---

## Citation

```bibtex
@article{cascam2024,
  title={CasCAM: Cascade Class Activation Mapping for Artifact-Robust Explainability},
  author={...},
  journal={...},
  year={2024}
}
```
