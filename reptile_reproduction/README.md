Experiment reproduces all Reptile results for settings from Table 1 and Table 2 from https://arxiv.org/abs/1803.02999
All experiments reproducing Omniglot results are tracked with Neptune:
https://app.neptune.ml/deepsense-ai-research/meta-learning-reptile/experiments
Experiments are marked with tag `reproduce`. Moreover all experiments are marked with a tag proper tag corresponding to reproduced setting:
```python
tags = [o15, o15t, o55, o55t, o120, o120t, o520, o520t, m15, m15t, m55, m55t]
```
Experiments with `mrunner` tag were produced with mrunner on Prometheus. Experiments with `local` tag were produced locally on a PC.

`omniglot.py` file contains setting used for producing results for Omniglot dataset.
`miniimagenet.py` file contains setting used for producing results for Mini-Imagenet dataset.

# Results
More results will appear here


Test Accuracy for Setting | o15 | o15t | o55 | o55t | o120 | o120t | o520 | o520t | m15 | m15t | m55 | m55t
--- | --- | --- | --- |--- |--- |--- |--- |--- |--- |--- |--- | ---
Publication | 95.39 ± 0.09% | 97.68 ± 0.04% | 98.90 ± 0.10% | 99.48 ± 0.06% | 88.14 ± 0.15% | 89.43 ± 0.14% | 96.65 ± 0.33% | 97.12 ± 0.32% | 47.07 ± 0.26% | 49.97 ± 0.32% | 62.74 ± 0.37% | 65.99 ± 0.58%
Local without Neptune | 0.95484 | 0.9774 | 0.98898 | 0.9952 | 0.881155 | 0.89296 | 0.965645 | 0.9755 | --- | --- | --- | ---
Prometheus with mrunner | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
