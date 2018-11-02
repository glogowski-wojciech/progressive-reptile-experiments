# Pretrained column

In this experiment we check how does a 2-columns progressive network with one pretrained column works. The pretrained column weights are from one-column training with original setting from publication. We try both pretraining 1st column and pretraining 2nd column. We also check learning rate of untrained column equal 0.0002, 0.001, 0.005. We test this algorithm on all tasks.

# Tags:

- `pretraining_col0` (for jobs that pretrain column 0)
- `pretraining_col1` (for jobs that pretrain column 1)
- `pret_col0` (for training with pretrained column 0)
- `pret_col1` (for training with pretrained column 1)
- `lr=0.0002` (for lr=0.0002 in untrained column)
- `lr=0.001` (for lr=0.001 in untrained column)
- `lr=0.005` (for lr=0.005 in untrained column)

Test accuracy for `pret_col0` | o15 | o15t | o55 | o55t | o120 | o120t | o520 | o520t | m15 | m15t | m55 | m55t
--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
`lr=0.0002` | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
`lr=0.001` | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
`lr=0.005` | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---

Test accuracy for `pret_col1` | o15 | o15t | o55 | o55t | o120 | o120t | o520 | o520t | m15 | m15t | m55 | m55t
--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
`lr=0.0002` | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
`lr=0.001` | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
`lr=0.005` | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
