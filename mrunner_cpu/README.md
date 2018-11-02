# On experiments
 
Tags:
- `intel_tf` (job using MKL-DNN)

Prometheus provides 2232 nodes, each with two Xeons E5-2680v3 12C 2,5 GHz. 72 nodes include two Tesla K40XL GPUs. Read [this](https://pl.wikipedia.org/wiki/Prometheus_(superkomputer)) for more details. Due to great number of CPU-only nodes, their availability is much better than availability of GPU nodes. It is reasonable to perform experiments on these nodes however, experiments turned out to run slow. This experiment compares time of execution of CPU run on Prometheus with regular TensorFlow 1.11 with time of execution of CPU run on Prometheus with TensorFlow 1.11 provided by Intel that includes MKL-DNN described [here](https://software.intel.com/en-us/articles/intel-optimization-for-tensorflow-installation-guide).

# Results

Time of execution | o15 | o15t | o55 | o55t | o120 | o120t | o520 | o520t | m15 | m15t | m55 | m55t
--- | --- | --- | --- |--- |--- |--- |--- |--- |--- |--- |--- | ---
TensorFlow 1.11 without MKL-DNN | --- | --- | --- |--- |--- |--- |--- |--- |--- |--- |--- | ---
TensorFlow 1.11 with MKL-DNN  | --- | --- | --- |--- |--- |--- |--- |--- |--- |--- |--- | ---