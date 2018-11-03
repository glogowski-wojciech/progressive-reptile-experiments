# Pretrained column

In this experiment we check how does a 2-columns progressive network with one pretrained column works. The pretrained column weights are from one-column training with original setting from publication. We pretrain column 0. We test in on `o15`, `o120`, `m15`, `m55` tasks. After loading the pretrained column we consider multiple learning rates of both column 0 and column 1.

# Tags:

- `pretraining_col0` (for jobs that pretrain column 0)
- `pretraining_col1` (for jobs that pretrain column 1)
- `pretrained_col0` (for training with pretrained column 0)


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
