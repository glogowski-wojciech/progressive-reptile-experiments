# Two meta learning rates

We use separate meta learning rates for progressive column 0 and progressive column 1. Goal of the experiment is to test whether any column can learn to store more long-term features and to find best meta learning rates. We test many values for initial meta step (ims) and final meta step (fms) for each column.

Each row in the tables represents (ims for progressive column 0, fms for progressive column 0)
Each column in the tables represents (ims for progressive column 1, fms for progressive column 1)

# Results

# Fast column 0:

Test Accuracy in o15 | (0.1, 0.1) | (1.0, 0.1)
--- | --- | ---
(0.1, 0.0) | --- | ---
(1.0, 0.0) | --- | ---

Test Accuracy in o55 | (0.1, 0.1) | (1.0, 0.1)
--- | --- | ---
(0.1, 0.0) | --- | ---
(1.0, 0.0) | --- | ---

Test Accuracy in o120 | (0.1, 0.1) | (1.0, 0.1)
--- | --- | ---
(0.1, 0.0) | --- | ---
(1.0, 0.0) | --- | ---

Test Accuracy in o520 | (0.1, 0.1) | (1.0, 0.1)
--- | --- | ---
(0.1, 0.0) | --- | ---
(1.0, 0.0) | --- | ---

Test Accuracy in m15 | (0.1, 0.1) | (1.0, 0.1)
--- | --- | ---
(0.1, 0.0) | --- | ---
(1.0, 0.0) | --- | ---

Test Accuracy in m55 | (0.1, 0.1) | (1.0, 0.1)
--- | --- | ---
(0.1, 0.0) | --- | ---
(1.0, 0.0) | --- | ---

# Fast column 1:

Test Accuracy in o15 | (0.1, 0.0) | (0.1, 0.1) | (0.1, 1.0) | (1.0, 0.0) | (1.0, 0.1) | (1.0, 1.0) | (10.0, 0.0) | (10.0, 0.1) | (10.0, 1.0)
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
(0.1, 0.0) | 0.92298 | 0.92642 | 0.87174 | 0.91742 | 0.9125 | 0.89114 | 0.85592 | 0.85928 | 0.85698
(1.0, 0.0) | 0.9455 | 0.92448 | 0.86078 | 0.96182 | 0.94604 | 0.85974 | 0.93182 | 0.93558 | 0.91542
(10.0, 0.0) | 0.9474 | 0.93258 | 0.9188 | 0.96338 | 0.95966 | 0.927 | 0.2 | 0.2 | 0.2

Test Accuracy in o55 | (0.1, 0.0) | (0.1, 0.1) | (0.1, 1.0) | (1.0, 0.0) | (1.0, 0.1) | (1.0, 1.0) | (10.0, 0.0) | (10.0, 0.1) | (10.0, 1.0)
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
(0.1, 0.0) | 0.98272 | 0.98608 | 0.97376 | 0.9861 | 0.98472 | 0.97594 | 0.96822 | 0.96678 | 0.96474
(1.0, 0.0) | 0.98674 | 0.98622 | 0.98794 | 0.99162 | 0.99214 | 0.98628 | 0.98434 | 0.98678 | 0.98582
(10.0, 0.0) | 0.98566 | 0.98802 | 0.98966 | 0.99294 | 0.99352 | 0.99096 | 0.2 | 0.79808 | 0.2

Test Accuracy in o120 | (0.1, 0.0) | (0.1, 0.1) | (0.1, 1.0) | (1.0, 0.0) | (1.0, 0.1) | (1.0, 1.0) | (10.0, 0.0) | (10.0, 0.1) | (10.0, 1.0)
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
(0.1, 0.0) | 0.882085 | 0.8773 | 0.79247 | 0.847435 | 0.83526 | 0.796715 | 0.791525 | 0.806495 | 0.8044
(1.0, 0.0) | 0.87883 | 0.87644 | 0.7513 | 0.89101 | 0.86895 | 0.75168 | 0.809925 | 0.807805 | 0.82721
(10.0, 0.0) | 0.87739 | 0.87378 | 0.81895 | 0.89204 | 0.8823 | 0.812995 | 0.05 | 0.05 | 0.05

Test Accuracy in o520 | (0.1, 0.0) | (0.1, 0.1) | (0.1, 1.0) | (1.0, 0.0) | (1.0, 0.1) | (1.0, 1.0) | (10.0, 0.0) | (10.0, 0.1) | (10.0, 1.0)
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
(0.1, 0.0) | 0.96467 | 0.966405 | 0.94623 | 0.9618 | --- | 0.938315 | 0.93836 | 0.944375 | 0.942415
(1.0, 0.0) | 0.96489 | 0.967685 | 0.95287 | 0.96675 | 0.967595 | 0.957655 | 0.95074 | 0.958895 | 0.951015
(10.0, 0.0) | 0.964455 | 0.96761 | 0.967575 | 0.97225 | 0.970165 | 0.96835 | 0.05 | 0.05 | 0.05

Test Accuracy in m15 | (0.1, 0.0) | (0.1, 0.1) | (0.1, 1.0) | (1.0, 0.0) | (1.0, 0.1) | (1.0, 1.0) | (10.0, 0.0) | (10.0, 0.1) | (10.0, 1.0)
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
(0.1, 0.0) | 0.47016 | 0.47592 | 0.40506 | 0.47922 | 0.46638 | 0.43018 | 0.2 | 0.44116 | 0.44208
(1.0, 0.0) | 0.484 | 0.47988 | 0.40556 | 0.4676 | 0.45554 | 0.40514 | 0.2 | 0.41706 | 0.2
(10.0, 0.0) | 0.49306 | 0.4719 | 0.42704 | 0.46274 | 0.46978 | 0.40752 | 0.2 | 0.2 | 0.2

Test Accuracy in m55 | (0.1, 0.0) | (0.1, 0.1) | (0.1, 1.0) | (1.0, 0.0) | (1.0, 0.1) | (1.0, 1.0) | (10.0, 0.0) | (10.0, 0.1) | (10.0, 1.0)
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
(0.1, 0.0) | 0.64206 | 0.65522 | 0.6382 | 0.64114 | 0.6343 | 0.60754 | 0.57814 | 0.56326 | 0.58722
(1.0, 0.0) | 0.65582 | 0.6567 | 0.62898 | 0.63138 | 0.62782 | 0.6196 | --- | --- | ---
(10.0, 0.0) | --- | --- | --- | --- | 0.65056 | --- | --- | --- | ---
