# Pretrained column

In this experiment we check how does a 2-columns progressive network with one pretrained column works. The pretrained column weights are from one-column training with original setting from publication. We pretrain column 0. We test in on `o15`, `o120`, `m15`, `m55` tasks. After loading the pretrained column we consider multiple learning rates of both column 0 and column 1.

# Tags

- `pretraining_col0` (for jobs that pretrain column 0)
- `pretraining_col1` (for jobs that pretrain column 1)
- `pretrained_col0` (for training with pretrained column 0)

# Results

Test Accuracy in o15 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.95194 | 0.96304 | 0.94214
lr0=0.001 | 0.94832 | 0.96488 | 0.92792
lr0=0.005 | 0.94902 | 0.96538 | 0.92106

Test Accuracy in o120 | lr1=0.0001 | lr1=0.0005 | lr1=0.0025
--- | --- | --- | ---
lr0=0.0001 | 0.87929 | --- | ---
lr0=0.0005 | --- | --- | 0.89101
lr0=0.0025 | --- | --- | ---

Test Accuracy in m15 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.46702 | 0.46662 | 0.46088
lr0=0.001 | 0.45396 | 0.44612 | 0.45132
lr0=0.005 | 0.45426 | 0.44686 | 0.45408

Test Accuracy in m55 | lr1=0.0002 | lr1=0.001 | lr1=0.005
--- | --- | --- | ---
lr0=0.0002 | 0.62368 | 62014 | 0.6123
lr0=0.001 | 0.62266 | 0.62104 | 0.62036
lr0=0.005 | 0.6225 | 0.62632 | 0.61404
