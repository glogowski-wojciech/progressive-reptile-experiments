# On experiments
 
Tags:
- `mrunner` (Prometheus with mrunner)
- `local` (local with Neptune)
- `one_column` (one progressive column)

Experiment reproduces all Reptile results for settings from Table 1 and Table 2 from https://arxiv.org/abs/1803.02999. All experiments reproducing Omniglot results are tracked with Neptune if not stated otherwise. One progressive column reproduces results with use of `Progressive[Omniglot|MiniImageNet]Column` class. The goal of the experiment is to ensure that Neptune, mrunner and new models consisting of `Progressive[Omniglot|MiniImageNet]Column` classes don't break anything in argument parsing, dataloading and training.

# Results

Test Accuracy for Setting | o15 | o15t | o55 | o55t | o120 | o120t | o520 | o520t | m15 | m15t | m55 | m55t
--- | --- | --- | --- |--- |--- |--- |--- |--- |--- |--- |--- | ---
Publication | 95.39 ± 0.09% | 97.68 ± 0.04% | 98.90 ± 0.10% | 99.48 ± 0.06% | 88.14 ± 0.15% | 89.43 ± 0.14% | 96.65 ± 0.33% | 97.12 ± 0.32% | 47.07 ± 0.26% | 49.97 ± 0.32% | 62.74 ± 0.37% | 65.99 ± 0.58%
Local without Neptune | 0.95484 | 0.9774 | 0.98898 | 0.9952 | 0.881155 | 0.89296 | 0.965645 | 0.9755 | --- | --- | --- | ---
Local with Neptune | 0.95556 | 0.9779 | 0.9901 | 0.99534 | 0.87928 | 0.89129 | 0.965305 | 0.970515 |0.46712 | 0.49952 | 0.62846 | 0.65802
Prometheus with mrunner | 0.95248 | 0.97614 | 0.99148 | 0.99528 | 0.88004 | 0.891275 | 0.965595 | 0.969905 | 0.47154 | 0.49234 | 0.6332 | 0.66136
One progressive column| 0.95202 | 0.97704 | 0.98888 | 0.99492 | --- | 0.8973 | 0.96472 | 0.97392 | 0.46272 | 0.50194 | 0.6365 | 0.65966
