# Two columns learning rate

We use separate learning rates for progressive column 0 and progressive column 1. Both gradients come from loss from columns 1 (none from column 0). Goal of this experiment is to find best learning rates for `o15` and `m15` tasks for two-column architecture. Default learning rate from publication used for one column is 0.001.

Test Accuracy in o15 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.90222 | 0.96016 | 0.90094
lr0=0.001 | 0.94098 | 0.96056 | 0.89822
lr0=0.005 | 0.93998 | 0.96158 | 0.92134

Test Accuracy in o120 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.892885 | 0.879715 | 0.82063
lr0=0.001 | 0.879255 | 0.874235 | 0.84805
lr0=0.005 | 0.875685 | 0.888225 | 0.850205

Test Accuracy in m15 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.46588 | 0.46234 | 0.44636
lr0=0.001 | 0.45464 | 0.46306 | 0.44806
lr0=0.005 | 0.45504 | 0.48112 | 0.44412

Test Accuracy in m55 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.63168 | 0.63084 | 0.61258
lr0=0.001 | 0.6297 | 0.63076 | 0.61506
lr0=0.005 | 0.63216 | 0.64586 | 0.62092
