# Meta learning, k-shot learning

*In few-shot classification tasks, we have a meta-dataset D containing many classes C, where each
class is itself a set of example instances {c1, c2, ..., cn}. If we are doing K-shot, N-way classification,
then we sample tasks by selecting N classes from C and then selecting K + 1 examples for each
class. We split these examples into a training set and a test set, where the test set contains a single
example for each class. The model gets to see the entire training set, and then it must classify a
randomly chosen sample from the test set. For example, if you trained a model for 5-shot, 5-way
classification, then you would show it 25 examples (5 per class) and ask it to classify a 26th example.*

~ source: "On First-Order Meta-Learning Algorithms", Nichol et al., https://arxiv.org/abs/1803.02999

# Progressive net

To quickly get it, check network scheme on page 2 from https://arxiv.org/abs/1606.04671
 
# Tags explained

Every experiment has exclusive tag which is also name of the directory.

Also each experiment is being tested on multiple meta-learning problems with corresponding tags:
 
```python
tags = [o15, o15t, o55, o55t, o120, o120t, o520, o520t, m15, m15t, m55, m55t]
```

tag ::= [o|m][1|5][5|20][|t]

[o|m]:
- o ::= omniglot
- m ::= miniimagenet

[1|5]:
- 1 ::= 1-shot
- 5 ::= 5-shot

[5|20]:
- 5 ::= 5-way
- 20 ::= 20-way (used only for Omniglot)

[|t]:
- '' ::= non-transductive setting
- 't' ::= transductive setting (in test use batches of test data, not single test image with rest of batch consisting of train data).


Experiments with `mrunner` tag were produced with mrunner on Prometheus. Experiments with `local` tag were produced locally on a PC. If not stated, it is easy to check where the experiment were run by checking `Experiment page on Neptune -> Sumary -> omniglot_src`. `/net/...` idicates that the experiment was run on Prometheus. Otherwise it was run locally.
