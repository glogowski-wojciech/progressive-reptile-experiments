# Two columns two losses

We use separate learning rates for progressive column 0 and progressive column 1. Gradients come from two losses. Gradient for column 0 comes from column 0's logits' loss. Gradient for column 1 comes from column 1's logits' loss. Goal of this experiment is to verify accuracy of this solution and to find best learning rates for `o15`, `o120`, `m15` and `m55` tasks. Default learning rate from publication used for one column is 0.001 for `o15`, `m15` and `m55` and 0.0005 for `o120`. Default number of meta-steps is 100,000 for `o15`, `m15` and `m55` and 200,000 for `o120`.

# Results

For given task and learning rates, results for column 0 and column 1 correspond to the same 2-column network.

Test Accuracy of column 0 in o15 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.85922 | 0.86072 | 0.85128
lr0=0.001 | 0.94982 | 0.9511 | 0.9532
lr0=0.005 | 0.91256 | 0.94418 | 0.89232

Test Accuracy of column 1 in o15 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.89866 | 0.95372 | 0.9237
lr0=0.001 | 0.9498 | 0.94624 | 0.94888
lr0=0.005 | 0.93298 | 0.95036 | 0.90848

Test Accuracy of column 0 in o120 | lr1=0.0001 | lr1=0.0005 | lr1=0.0025
--- | --- | --- | ---
lr0=0.0001 | 0.687335 | 0.67348 | 0.636885
lr0=0.0005 | 0.87855 | 0.879045 | 0.874515
lr0=0.0025 | 0.869795 | 0.862385 | 0.870475

Test Accuracy of column 1 in o120 | lr1=0.0001 | lr1=0.0005 | lr1=0.0025
--- | --- | --- | ---
lr0=0.0001 | 0.764795 | 0.87225 | 0.865705
lr0=0.0005 | 0.878215 | 0.87734 | 0.86736
lr0=0.0025 | 0.871415 | 0.86063 | 0.869445

Test Accuracy of column 0 in m15 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.43236 | 0.43156 | 0.43858
lr0=0.001 | 0.47904 | 0.46794 | 0.4781
lr0=0.005 | 0.45732 | 0.44992 | 0.46186

Test Accuracy of column 1 in m15 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.4647 | 0.46736 | 0.4631
lr0=0.001 | 0.47816 | 0.46446 | 0.4617
lr0=0.005 | 0.46078 | 0.45934 | 0.45896

Test Accuracy of column 0 in m55 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.58406 | 0.58218 | 0.58626
lr0=0.001 | 0.63 | 0.62602 | 0.62886
lr0=0.005 | 0.62386 | 0.62372 | 0.6203

Test Accuracy of column 1 in m55 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.62252 | 0.63432 | 0.62504
lr0=0.001 | 0.62996 | 0.62374 | 0.62758
lr0=0.005 | 0.62802 | 0.61932 | 0.6202
