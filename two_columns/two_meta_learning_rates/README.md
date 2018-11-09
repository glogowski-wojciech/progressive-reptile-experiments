# Two meta learning rates

We use separate meta learning rates for progressive column 0 and progressive column 1. Goal of the experiment is to test whether any column can learn to store more long-term features and to find best meta learning rates. We test many values for initial meta step (ims) and final meta step (fms) for each column.

Each row in the tables represents (ims for progressive column0, fms for progressive columns 0)
Each column in the tables represents (ims for progressive column1, fms for progressive columns 1)

# Results

Fast column 1:

Test Accuracy in o15 | (0.1, 0.0) | (0.1, 0.1) | (0.1, 1.0) | (1.0, 0.0) | (1.0, 0.1) | (1.0, 1.0) | (10.0, 0.0) | (10.0, 0.1) | (10.0, 1.0)
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
(0.1, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---
(1.0, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---
(10.0, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---

Test Accuracy in o55 | (0.1, 0.0) | (0.1, 0.1) | (0.1, 1.0) | (1.0, 0.0) | (1.0, 0.1) | (1.0, 1.0) | (10.0, 0.0) | (10.0, 0.1) | (10.0, 1.0)
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
(0.1, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---
(1.0, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---
(10.0, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---

Test Accuracy in o120 | (0.1, 0.0) | (0.1, 0.1) | (0.1, 1.0) | (1.0, 0.0) | (1.0, 0.1) | (1.0, 1.0) | (10.0, 0.0) | (10.0, 0.1) | (10.0, 1.0)
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
(0.1, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---
(1.0, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---
(10.0, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---

Test Accuracy in o520 | (0.1, 0.0) | (0.1, 0.1) | (0.1, 1.0) | (1.0, 0.0) | (1.0, 0.1) | (1.0, 1.0) | (10.0, 0.0) | (10.0, 0.1) | (10.0, 1.0)
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
(0.1, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---
(1.0, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---
(10.0, 0.0) | --- | --- | --- | --- | --- | --- | --- | --- | ---
