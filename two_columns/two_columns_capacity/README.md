# Two columns capacity

Two-column network has more than 2 times more parameters than original network (2 times + lateral connections). In this experiment we lower number of channels to get a little lower number of parameters than in the original network. In this way we can later check check how much capacity to store information has such architecture of nework and we comapre this with architecture of original network.

Experiments conducted locally with such a piece of code inserted after model creation:
```python
    num_params = np.sum([np.prod(v.get_shape().as_list()) for v in tf.trainable_variables()])
    vars_nums = [(v, v.get_shape().as_list()) for v in tf.trainable_variables()]
    for v, sh in vars_nums:
        print(v, sh)
    print('num_params: ', num_params)
    return 0
```

Number of parameters in original code:

- Original Omniglot: 113221
- Original Mini-ImageNet: 34661
- Two-column Omniglot: 353673
- Two-Column Mini-ImageNet: 101193

Number of convolutional channels in two-column nets that make number of parameters closest to the original number of parameters:

- Omniglot: 36 (113265 parameters)
- Mini-ImageNet: 18 (35505 parameters)

Number of convolutional channels in two-column nets with `oxxo` lateral map that make number of parameters closest to the original number of parameters:

- Omniglot: 41 (111773 parameters)
- Mini-ImageNet: 21 (34069 parameters)

# Full logs

Original Omniglot:
```
<tf.Variable 'conv2d/kernel:0' shape=(3, 3, 1, 64) dtype=float32_ref> [3, 3, 1, 64]
<tf.Variable 'conv2d/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'batch_normalization/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'batch_normalization/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'conv2d_1/kernel:0' shape=(3, 3, 64, 64) dtype=float32_ref> [3, 3, 64, 64]
<tf.Variable 'conv2d_1/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'batch_normalization_1/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'batch_normalization_1/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'conv2d_2/kernel:0' shape=(3, 3, 64, 64) dtype=float32_ref> [3, 3, 64, 64]
<tf.Variable 'conv2d_2/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'batch_normalization_2/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'batch_normalization_2/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'conv2d_3/kernel:0' shape=(3, 3, 64, 64) dtype=float32_ref> [3, 3, 64, 64]
<tf.Variable 'conv2d_3/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'batch_normalization_3/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'batch_normalization_3/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'dense/kernel:0' shape=(256, 5) dtype=float32_ref> [256, 5]
<tf.Variable 'dense/bias:0' shape=(5,) dtype=float32_ref> [5]
num_params:  113221
```

Original Mini-ImageNet:
```
<tf.Variable 'conv2d/kernel:0' shape=(3, 3, 3, 32) dtype=float32_ref> [3, 3, 3, 32]
<tf.Variable 'conv2d/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'batch_normalization/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'batch_normalization/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'conv2d_1/kernel:0' shape=(3, 3, 32, 32) dtype=float32_ref> [3, 3, 32, 32]
<tf.Variable 'conv2d_1/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'batch_normalization_1/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'batch_normalization_1/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'conv2d_2/kernel:0' shape=(3, 3, 32, 32) dtype=float32_ref> [3, 3, 32, 32]
<tf.Variable 'conv2d_2/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'batch_normalization_2/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'batch_normalization_2/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'conv2d_3/kernel:0' shape=(3, 3, 32, 32) dtype=float32_ref> [3, 3, 32, 32]
<tf.Variable 'conv2d_3/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'batch_normalization_3/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'batch_normalization_3/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'dense/kernel:0' shape=(1152, 5) dtype=float32_ref> [1152, 5]
<tf.Variable 'dense/bias:0' shape=(5,) dtype=float32_ref> [5]
num_params:  34661.0
```

Two-column Omniglot:
```
<tf.Variable 'Col0Vars/conv2d/kernel:0' shape=(3, 3, 1, 64) dtype=float32_ref> [3, 3, 1, 64]
<tf.Variable 'Col0Vars/conv2d/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col0Vars/batch_normalization/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col0Vars/batch_normalization/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col0Vars/conv2d_1/kernel:0' shape=(3, 3, 64, 64) dtype=float32_ref> [3, 3, 64, 64]
<tf.Variable 'Col0Vars/conv2d_1/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col0Vars/batch_normalization_1/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col0Vars/batch_normalization_1/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col0Vars/conv2d_2/kernel:0' shape=(3, 3, 64, 64) dtype=float32_ref> [3, 3, 64, 64]
<tf.Variable 'Col0Vars/conv2d_2/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col0Vars/batch_normalization_2/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col0Vars/batch_normalization_2/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col0Vars/conv2d_3/kernel:0' shape=(3, 3, 64, 64) dtype=float32_ref> [3, 3, 64, 64]
<tf.Variable 'Col0Vars/conv2d_3/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col0Vars/batch_normalization_3/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col0Vars/batch_normalization_3/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/conv2d/kernel:0' shape=(3, 3, 1, 64) dtype=float32_ref> [3, 3, 1, 64]
<tf.Variable 'Col1Vars/conv2d/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/batch_normalization/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/batch_normalization/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Net/Col1Vars/C2CAdapt/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_1/kernel:0' shape=(1, 1, 64, 64) dtype=float32_ref> [1, 1, 64, 64]
<tf.Variable 'Col1Vars/conv2d_1/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/conv2d_2/kernel:0' shape=(3, 3, 128, 64) dtype=float32_ref> [3, 3, 128, 64]
<tf.Variable 'Col1Vars/conv2d_2/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/batch_normalization_1/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/batch_normalization_1/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Net/Col1Vars/C2CAdapt_1/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_3/kernel:0' shape=(1, 1, 64, 64) dtype=float32_ref> [1, 1, 64, 64]
<tf.Variable 'Col1Vars/conv2d_3/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/conv2d_4/kernel:0' shape=(3, 3, 128, 64) dtype=float32_ref> [3, 3, 128, 64]
<tf.Variable 'Col1Vars/conv2d_4/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/batch_normalization_2/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/batch_normalization_2/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Net/Col1Vars/C2CAdapt_2/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_5/kernel:0' shape=(1, 1, 64, 64) dtype=float32_ref> [1, 1, 64, 64]
<tf.Variable 'Col1Vars/conv2d_5/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/conv2d_6/kernel:0' shape=(3, 3, 128, 64) dtype=float32_ref> [3, 3, 128, 64]
<tf.Variable 'Col1Vars/conv2d_6/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/batch_normalization_3/gamma:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/batch_normalization_3/beta:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Net/Col1Vars/C2LAdapt/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_7/kernel:0' shape=(1, 1, 64, 64) dtype=float32_ref> [1, 1, 64, 64]
<tf.Variable 'Col1Vars/conv2d_7/bias:0' shape=(64,) dtype=float32_ref> [64]
<tf.Variable 'Col1Vars/dense/kernel:0' shape=(512, 5) dtype=float32_ref> [512, 5]
<tf.Variable 'Col1Vars/dense/bias:0' shape=(5,) dtype=float32_ref> [5]
num_params:  353673.0
```

Two-column Mini-ImageNet:
```
<tf.Variable 'Col0Vars/conv2d/kernel:0' shape=(3, 3, 3, 32) dtype=float32_ref> [3, 3, 3, 32]
<tf.Variable 'Col0Vars/conv2d/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col0Vars/batch_normalization/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col0Vars/batch_normalization/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col0Vars/conv2d_1/kernel:0' shape=(3, 3, 32, 32) dtype=float32_ref> [3, 3, 32, 32]
<tf.Variable 'Col0Vars/conv2d_1/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col0Vars/batch_normalization_1/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col0Vars/batch_normalization_1/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col0Vars/conv2d_2/kernel:0' shape=(3, 3, 32, 32) dtype=float32_ref> [3, 3, 32, 32]
<tf.Variable 'Col0Vars/conv2d_2/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col0Vars/batch_normalization_2/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col0Vars/batch_normalization_2/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col0Vars/conv2d_3/kernel:0' shape=(3, 3, 32, 32) dtype=float32_ref> [3, 3, 32, 32]
<tf.Variable 'Col0Vars/conv2d_3/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col0Vars/batch_normalization_3/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col0Vars/batch_normalization_3/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/conv2d/kernel:0' shape=(3, 3, 3, 32) dtype=float32_ref> [3, 3, 3, 32]
<tf.Variable 'Col1Vars/conv2d/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/batch_normalization/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/batch_normalization/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Net/Col1Vars/C2CAdapt/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_1/kernel:0' shape=(1, 1, 32, 32) dtype=float32_ref> [1, 1, 32, 32]
<tf.Variable 'Col1Vars/conv2d_1/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/conv2d_2/kernel:0' shape=(3, 3, 64, 32) dtype=float32_ref> [3, 3, 64, 32]
<tf.Variable 'Col1Vars/conv2d_2/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/batch_normalization_1/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/batch_normalization_1/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Net/Col1Vars/C2CAdapt_1/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_3/kernel:0' shape=(1, 1, 32, 32) dtype=float32_ref> [1, 1, 32, 32]
<tf.Variable 'Col1Vars/conv2d_3/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/conv2d_4/kernel:0' shape=(3, 3, 64, 32) dtype=float32_ref> [3, 3, 64, 32]
<tf.Variable 'Col1Vars/conv2d_4/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/batch_normalization_2/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/batch_normalization_2/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Net/Col1Vars/C2CAdapt_2/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_5/kernel:0' shape=(1, 1, 32, 32) dtype=float32_ref> [1, 1, 32, 32]
<tf.Variable 'Col1Vars/conv2d_5/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/conv2d_6/kernel:0' shape=(3, 3, 64, 32) dtype=float32_ref> [3, 3, 64, 32]
<tf.Variable 'Col1Vars/conv2d_6/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/batch_normalization_3/gamma:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/batch_normalization_3/beta:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Net/Col1Vars/C2LAdapt/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_7/kernel:0' shape=(1, 1, 32, 32) dtype=float32_ref> [1, 1, 32, 32]
<tf.Variable 'Col1Vars/conv2d_7/bias:0' shape=(32,) dtype=float32_ref> [32]
<tf.Variable 'Col1Vars/dense/kernel:0' shape=(2304, 5) dtype=float32_ref> [2304, 5]
<tf.Variable 'Col1Vars/dense/bias:0' shape=(5,) dtype=float32_ref> [5]
num_params:  101193.0
```

Two-column Omniglot with 36 convolutional channels instead of 64:
```
<tf.Variable 'Col0Vars/conv2d/kernel:0' shape=(3, 3, 1, 36) dtype=float32_ref> [3, 3, 1, 36]
<tf.Variable 'Col0Vars/conv2d/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/batch_normalization/gamma:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/batch_normalization/beta:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/conv2d_1/kernel:0' shape=(3, 3, 36, 36) dtype=float32_ref> [3, 3, 36, 36]
<tf.Variable 'Col0Vars/conv2d_1/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/batch_normalization_1/gamma:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/batch_normalization_1/beta:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/conv2d_2/kernel:0' shape=(3, 3, 36, 36) dtype=float32_ref> [3, 3, 36, 36]
<tf.Variable 'Col0Vars/conv2d_2/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/batch_normalization_2/gamma:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/batch_normalization_2/beta:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/conv2d_3/kernel:0' shape=(3, 3, 36, 36) dtype=float32_ref> [3, 3, 36, 36]
<tf.Variable 'Col0Vars/conv2d_3/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/batch_normalization_3/gamma:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/batch_normalization_3/beta:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col0Vars/dense/kernel:0' shape=(144, 5) dtype=float32_ref> [144, 5]
<tf.Variable 'Col0Vars/dense/bias:0' shape=(5,) dtype=float32_ref> [5]
<tf.Variable 'Col1Vars/conv2d/kernel:0' shape=(3, 3, 1, 36) dtype=float32_ref> [3, 3, 1, 36]
<tf.Variable 'Col1Vars/conv2d/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/batch_normalization/gamma:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/batch_normalization/beta:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Net/Col1Vars/C2CAdapt/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_1/kernel:0' shape=(1, 1, 36, 36) dtype=float32_ref> [1, 1, 36, 36]
<tf.Variable 'Col1Vars/conv2d_1/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/conv2d_2/kernel:0' shape=(3, 3, 72, 36) dtype=float32_ref> [3, 3, 72, 36]
<tf.Variable 'Col1Vars/conv2d_2/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/batch_normalization_1/gamma:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/batch_normalization_1/beta:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Net/Col1Vars/C2CAdapt_1/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_3/kernel:0' shape=(1, 1, 36, 36) dtype=float32_ref> [1, 1, 36, 36]
<tf.Variable 'Col1Vars/conv2d_3/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/conv2d_4/kernel:0' shape=(3, 3, 72, 36) dtype=float32_ref> [3, 3, 72, 36]
<tf.Variable 'Col1Vars/conv2d_4/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/batch_normalization_2/gamma:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/batch_normalization_2/beta:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Net/Col1Vars/C2CAdapt_2/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_5/kernel:0' shape=(1, 1, 36, 36) dtype=float32_ref> [1, 1, 36, 36]
<tf.Variable 'Col1Vars/conv2d_5/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/conv2d_6/kernel:0' shape=(3, 3, 72, 36) dtype=float32_ref> [3, 3, 72, 36]
<tf.Variable 'Col1Vars/conv2d_6/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/batch_normalization_3/gamma:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/batch_normalization_3/beta:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Net/Col1Vars/C2LAdapt/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_7/kernel:0' shape=(1, 1, 36, 36) dtype=float32_ref> [1, 1, 36, 36]
<tf.Variable 'Col1Vars/conv2d_7/bias:0' shape=(36,) dtype=float32_ref> [36]
<tf.Variable 'Col1Vars/dense/kernel:0' shape=(288, 5) dtype=float32_ref> [288, 5]
<tf.Variable 'Col1Vars/dense/bias:0' shape=(5,) dtype=float32_ref> [5]
num_params:  113990.0
```

Two-column Mini-ImageNet with 18 convolutional channels instead of 32:
```
<tf.Variable 'Col0Vars/conv2d/kernel:0' shape=(3, 3, 3, 18) dtype=float32_ref> [3, 3, 3, 18]
<tf.Variable 'Col0Vars/conv2d/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col0Vars/batch_normalization/gamma:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col0Vars/batch_normalization/beta:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col0Vars/conv2d_1/kernel:0' shape=(3, 3, 18, 18) dtype=float32_ref> [3, 3, 18, 18]
<tf.Variable 'Col0Vars/conv2d_1/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col0Vars/batch_normalization_1/gamma:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col0Vars/batch_normalization_1/beta:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col0Vars/conv2d_2/kernel:0' shape=(3, 3, 18, 18) dtype=float32_ref> [3, 3, 18, 18]
<tf.Variable 'Col0Vars/conv2d_2/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col0Vars/batch_normalization_2/gamma:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col0Vars/batch_normalization_2/beta:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col0Vars/conv2d_3/kernel:0' shape=(3, 3, 18, 18) dtype=float32_ref> [3, 3, 18, 18]
<tf.Variable 'Col0Vars/conv2d_3/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col0Vars/batch_normalization_3/gamma:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col0Vars/batch_normalization_3/beta:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/conv2d/kernel:0' shape=(3, 3, 3, 18) dtype=float32_ref> [3, 3, 3, 18]
<tf.Variable 'Col1Vars/conv2d/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/batch_normalization/gamma:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/batch_normalization/beta:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Net/Col1Vars/C2CAdapt/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_1/kernel:0' shape=(1, 1, 18, 18) dtype=float32_ref> [1, 1, 18, 18]
<tf.Variable 'Col1Vars/conv2d_1/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/conv2d_2/kernel:0' shape=(3, 3, 36, 18) dtype=float32_ref> [3, 3, 36, 18]
<tf.Variable 'Col1Vars/conv2d_2/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/batch_normalization_1/gamma:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/batch_normalization_1/beta:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Net/Col1Vars/C2CAdapt_1/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_3/kernel:0' shape=(1, 1, 18, 18) dtype=float32_ref> [1, 1, 18, 18]
<tf.Variable 'Col1Vars/conv2d_3/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/conv2d_4/kernel:0' shape=(3, 3, 36, 18) dtype=float32_ref> [3, 3, 36, 18]
<tf.Variable 'Col1Vars/conv2d_4/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/batch_normalization_2/gamma:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/batch_normalization_2/beta:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Net/Col1Vars/C2CAdapt_2/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_5/kernel:0' shape=(1, 1, 18, 18) dtype=float32_ref> [1, 1, 18, 18]
<tf.Variable 'Col1Vars/conv2d_5/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/conv2d_6/kernel:0' shape=(3, 3, 36, 18) dtype=float32_ref> [3, 3, 36, 18]
<tf.Variable 'Col1Vars/conv2d_6/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/batch_normalization_3/gamma:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/batch_normalization_3/beta:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Net/Col1Vars/C2LAdapt/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_7/kernel:0' shape=(1, 1, 18, 18) dtype=float32_ref> [1, 1, 18, 18]
<tf.Variable 'Col1Vars/conv2d_7/bias:0' shape=(18,) dtype=float32_ref> [18]
<tf.Variable 'Col1Vars/dense/kernel:0' shape=(1296, 5) dtype=float32_ref> [1296, 5]
<tf.Variable 'Col1Vars/dense/bias:0' shape=(5,) dtype=float32_ref> [5]
num_params:  35505.0
```

Two-column `oxxo` Omniglot with 41 convolutional channels:

```
<tf.Variable 'Col0Vars/conv2d/kernel:0' shape=(3, 3, 1, 41) dtype=float32_ref> [3, 3, 1, 41]
<tf.Variable 'Col0Vars/conv2d/bias:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col0Vars/batch_normalization/gamma:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col0Vars/batch_normalization/beta:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col0Vars/conv2d_1/kernel:0' shape=(3, 3, 41, 41) dtype=float32_ref> [3, 3, 41, 41]
<tf.Variable 'Col0Vars/conv2d_1/bias:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col0Vars/batch_normalization_1/gamma:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col0Vars/batch_normalization_1/beta:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col0Vars/conv2d_2/kernel:0' shape=(3, 3, 41, 41) dtype=float32_ref> [3, 3, 41, 41]
<tf.Variable 'Col0Vars/conv2d_2/bias:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col0Vars/batch_normalization_2/gamma:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col0Vars/batch_normalization_2/beta:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/conv2d/kernel:0' shape=(3, 3, 1, 41) dtype=float32_ref> [3, 3, 1, 41]
<tf.Variable 'Col1Vars/conv2d/bias:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/batch_normalization/gamma:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/batch_normalization/beta:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/conv2d_1/kernel:0' shape=(3, 3, 41, 41) dtype=float32_ref> [3, 3, 41, 41]
<tf.Variable 'Col1Vars/conv2d_1/bias:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/batch_normalization_1/gamma:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/batch_normalization_1/beta:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Net/Col1Vars/C2CAdapt_1/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_2/kernel:0' shape=(1, 1, 41, 41) dtype=float32_ref> [1, 1, 41, 41]
<tf.Variable 'Col1Vars/conv2d_2/bias:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/conv2d_3/kernel:0' shape=(3, 3, 82, 41) dtype=float32_ref> [3, 3, 82, 41]
<tf.Variable 'Col1Vars/conv2d_3/bias:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/batch_normalization_2/gamma:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/batch_normalization_2/beta:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Net/Col1Vars/C2CAdapt_2/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_4/kernel:0' shape=(1, 1, 41, 41) dtype=float32_ref> [1, 1, 41, 41]
<tf.Variable 'Col1Vars/conv2d_4/bias:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/conv2d_5/kernel:0' shape=(3, 3, 82, 41) dtype=float32_ref> [3, 3, 82, 41]
<tf.Variable 'Col1Vars/conv2d_5/bias:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/batch_normalization_3/gamma:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/batch_normalization_3/beta:0' shape=(41,) dtype=float32_ref> [41]
<tf.Variable 'Col1Vars/dense/kernel:0' shape=(164, 5) dtype=float32_ref> [164, 5]
<tf.Variable 'Col1Vars/dense/bias:0' shape=(5,) dtype=float32_ref> [5]
num_params:  111773.0
```

Two-column `oxxo` Mini-ImageNet with 21 convolutional channels:

```
<tf.Variable 'Col0Vars/conv2d/kernel:0' shape=(3, 3, 3, 21) dtype=float32_ref> [3, 3, 3, 21]
<tf.Variable 'Col0Vars/conv2d/bias:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col0Vars/batch_normalization/gamma:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col0Vars/batch_normalization/beta:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col0Vars/conv2d_1/kernel:0' shape=(3, 3, 21, 21) dtype=float32_ref> [3, 3, 21, 21]
<tf.Variable 'Col0Vars/conv2d_1/bias:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col0Vars/batch_normalization_1/gamma:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col0Vars/batch_normalization_1/beta:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col0Vars/conv2d_2/kernel:0' shape=(3, 3, 21, 21) dtype=float32_ref> [3, 3, 21, 21]
<tf.Variable 'Col0Vars/conv2d_2/bias:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col0Vars/batch_normalization_2/gamma:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col0Vars/batch_normalization_2/beta:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/conv2d/kernel:0' shape=(3, 3, 3, 21) dtype=float32_ref> [3, 3, 3, 21]
<tf.Variable 'Col1Vars/conv2d/bias:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/batch_normalization/gamma:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/batch_normalization/beta:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/conv2d_1/kernel:0' shape=(3, 3, 21, 21) dtype=float32_ref> [3, 3, 21, 21]
<tf.Variable 'Col1Vars/conv2d_1/bias:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/batch_normalization_1/gamma:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/batch_normalization_1/beta:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Net/Col1Vars/C2CAdapt_1/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_2/kernel:0' shape=(1, 1, 21, 21) dtype=float32_ref> [1, 1, 21, 21]
<tf.Variable 'Col1Vars/conv2d_2/bias:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/conv2d_3/kernel:0' shape=(3, 3, 42, 21) dtype=float32_ref> [3, 3, 42, 21]
<tf.Variable 'Col1Vars/conv2d_3/bias:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/batch_normalization_2/gamma:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/batch_normalization_2/beta:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Net/Col1Vars/C2CAdapt_2/Variable:0' shape=() dtype=float32_ref> []
<tf.Variable 'Col1Vars/conv2d_4/kernel:0' shape=(1, 1, 21, 21) dtype=float32_ref> [1, 1, 21, 21]
<tf.Variable 'Col1Vars/conv2d_4/bias:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/conv2d_5/kernel:0' shape=(3, 3, 42, 21) dtype=float32_ref> [3, 3, 42, 21]
<tf.Variable 'Col1Vars/conv2d_5/bias:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/batch_normalization_3/gamma:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/batch_normalization_3/beta:0' shape=(21,) dtype=float32_ref> [21]
<tf.Variable 'Col1Vars/dense/kernel:0' shape=(756, 5) dtype=float32_ref> [756, 5]
<tf.Variable 'Col1Vars/dense/bias:0' shape=(5,) dtype=float32_ref> [5]
num_params:  34069.0
```
