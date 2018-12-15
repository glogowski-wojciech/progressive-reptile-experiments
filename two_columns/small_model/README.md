# Small model

We train two-column network with learning rates of columns 0 and 1 equal 0.005 and 0.001 respectively and with lateral scheme oxxo. The loss comes from column 1. The size of the network is similar to original size of networks used in Reptile as calculated in two_columns_capacity.

Mode | Accuracy | Accuracy of one-column network from Reptile
--- | --- | ---
o15 | 96.042 | 95.39 ± 0.09%
o15t | 97.986 | 97.68 ± 0.04%
o55 | 99.014 | 98.90 ± 0.10%
o55t | 99.542 | 99.48 ± 0.06%
o120 | 89.3855 | 88.14 ± 0.15%
o120t | 90.366 | 89.43 ± 0.14%
o520 | 96.603 | 96.65 ± 0.33%
o520t | 97.2495 | 97.12 ± 0.32%
m15 | 47.01 | 47.07 ± 0.26%
m15t | 50.004 | 49.97 ± 0.32%
m55 | 64.466 | 62.74 ± 0.37%
m55t | 66.546 | 65.99 ± 0.58%
