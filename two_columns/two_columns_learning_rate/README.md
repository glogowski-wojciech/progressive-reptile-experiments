# Two columns learning rate

We use separate learning rates for progressive column 0 and progressive column 1. Goal of this experiment is to find best learning rates for `o15` and `m15` tasks for two-column architecture. Default learning rate from publication used for one column is 0.001.

Test Accuracy in o15 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.90222 | 0.96016 | 0.90094
lr0=0.001 | 0.94098 | 0.96056 | 0.89822
lr0=0.005 | 0.93998 | 0.96158 | 0.92134

Test Accuracy in o120 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | --- | --- | ---
lr0=0.001 | --- | --- | ---
lr0=0.005 | --- | --- | ---

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
