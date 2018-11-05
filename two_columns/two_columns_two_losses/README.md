# Two columns two losses

We use separate learning rates for progressive column 0 and progressive column 1. Gradients come from two losses. Gradient for column 0 comes from column 0's logits' loss. Gradient for column 1 comes from column 1's logits' loss. Goal of this experiment is to verify accuracy of this solution and to find best learning rates for `o15`, `o120`, `m15` and `m55` tasks. Default learning rate from publication used for one column is 0.001 for `o15`, `m15` and `m55` and 0.0005 for `o120`. Default number of meta-steps is 100,000 for `o15`, `m15` and `m55` and 200,000 for `o120`.

Test Accuracy in o15 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | --- | --- | ---
lr0=0.001 | --- | --- | ---
lr0=0.005 | --- | --- | ---

Test Accuracy in o120 | lr1=0.0001 | lr1=0.0005 | lr1=0.0025
--- | --- | --- | ---
lr0=0.0001 | --- | --- | ---
lr0=0.0005 | --- | --- | ---
lr0=0.0025 | --- | --- | ---

Test Accuracy in m15 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | --- | --- | ---
lr0=0.001 | --- | --- | ---
lr0=0.005 | --- | --- | ---

Test Accuracy in m55 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | --- | --- | ---
lr0=0.001 | --- | --- | ---
lr0=0.005 | --- | --- | ---
