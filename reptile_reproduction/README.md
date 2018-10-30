# Meta learning? 1-shot 5-way? What is it?

*In few-shot classification tasks, we have a meta-dataset D containing many classes C, where each
class is itself a set of example instances {c1, c2, ..., cn}. If we are doing K-shot, N-way classification,
then we sample tasks by selecting N classes from C and then selecting K + 1 examples for each
class. We split these examples into a training set and a test set, where the test set contains a single
example for each class. The model gets to see the entire training set, and then it must classify a
randomly chosen sample from the test set. For example, if you trained a model for 5-shot, 5-way
classification, then you would show it 25 examples (5 per class) and ask it to classify a 26th example.*

~ source: "On First-Order Meta-Learning Algorithms", Nichol et al., https://arxiv.org/abs/1803.02999
 
# On experiments
 
Experiment reproduces all Reptile results for settings from Table 1 and Table 2 from https://arxiv.org/abs/1803.02999
All experiments reproducing Omniglot results are tracked with Neptune. All Neptune runs are integrated with git and non-dirty:
https://app.neptune.ml/deepsense-ai-research/meta-learning-reptile/experiments
Experiments are marked with tag `reproduce`. Moreover all experiments are marked with a tag proper tag corresponding to reproduced setting:
```python
tags = [o15, o15t, o55, o55t, o120, o120t, o520, o520t, m15, m15t, m55, m55t]
```

# Tags explained

tag ::= [o|m][1|5][5|20][|t]

[o|m]:
- o ::= omniglot
- m ::= miniimagenet

[1:5]:
- 1 ::= 1-shot
- 5 ::= 5-shot

[5|20]:
- 5 ::= 5-way
- 20 ::= 20-way

[|t]:
- '' ::= non-transductive setting
- 't' ::= transductive setting (in test use batches of test data, not single test image with rest of batch consisting of train data).


Experiments with `mrunner` tag were produced with mrunner on Prometheus. Experiments with `local` tag were produced locally on a PC.

`omniglot.py` file contains setting used for producing results for Omniglot dataset.
`miniimagenet.py` file contains setting used for producing results for Mini-Imagenet dataset.

# Results
More results will appear here


Test Accuracy for Setting | o15 | o15t | o55 | o55t | o120 | o120t | o520 | o520t | m15 | m15t | m55 | m55t
--- | --- | --- | --- |--- |--- |--- |--- |--- |--- |--- |--- | ---
Publication | 95.39 ± 0.09% | 97.68 ± 0.04% | 98.90 ± 0.10% | 99.48 ± 0.06% | 88.14 ± 0.15% | 89.43 ± 0.14% | 96.65 ± 0.33% | 97.12 ± 0.32% | 47.07 ± 0.26% | 49.97 ± 0.32% | 62.74 ± 0.37% | 65.99 ± 0.58%
Local without Neptune | 0.95484 | 0.9774 | 0.98898 | 0.9952 | 0.881155 | 0.89296 | 0.965645 | 0.9755 | --- | --- | --- | ---
Local with Neptune | 0.95556 | 0.9779 | 0.9901 | 0.99534 | 0.87928 | 0.89129 | 0.965305 | 0.970515 | --- | --- | --- | ---
Prometheus with mrunner | 0.95248 | 0.97614 | 0.99148 | 0.99528 | 0.88004 | 0.891275 | 0.965595 | 0.969905 | 0.47154 | 0.49234 | 0.6332 | 0.66136
