# On experiments
 
Tags:
- `intel_tf` (for jobs using MKL-DNN)
- `c6` (for jobs using MKL-DNN and 6 cores)
- `c12` (for jobs using MKL-DNN and 12 cores)
- `c24` (for jobs using MKL-DNN and 24 cores)

Prometheus provides 2232 nodes, each with two Xeons E5-2680v3 12C 2,5 GHz. 72 nodes include two Tesla K40XL GPUs. Read [this](https://pl.wikipedia.org/wiki/Prometheus_(superkomputer)) for more details. Due to great number of CPU-only nodes, their availability is much better than availability of GPU nodes. It is reasonable to perform experiments on these nodes however, experiments turned out to run slow. This experiment compares time of execution of CPU-only run on Prometheus with regular TensorFlow 1.11 with time of execution of CPU-only run on Prometheus with TensorFlow 1.11 provided by Intel that includes MKL-DNN described [here](https://software.intel.com/en-us/articles/intel-optimization-for-tensorflow-installation-guide) in order to check if it is feasible to run experiments on CPU-only nodes.

# Experiment settings

We test runs on CPU-only nodes using 2 (`intel_tf`) or 6 (`c6`) or 12 (`c12`) or 24 cores (`c24`) of node instead of mrunner's default 2 cores with MKL-DNN. We also test a 2-core run without MKL-DNN (no special tag).

# Run details
Experiment reproduces original Reptile's results on Prometheus with mrunner and Neptune. Time of execution is being tracked by Neptune.

# Results

Time of execution [h] | o15 | o15t | o55 | o55t | o120 | o120t | o520 | o520t | m15 | m15t | m55 | m55t
--- | --- | --- | --- |--- |--- |--- | --- | --- | --- | --- | --- | ---
TensorFlow 1.11 without MKL-DNN, c=2 | 27 | 27 | 26 | 16 | --- | --- | --- | --- | >48* | >48* | >48* | >48*
TensorFlow 1.11 with MKL-DNN, c=2  | --- | --- | --- |--- | --- | --- | --- | --- | --- | --- | --- | ---
TensorFlow 1.11 with MKL-DNN, c=6  | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
TensorFlow 1.11 with MKL-DNN, c=12  | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- 
TensorFlow 1.11 with MKL-DNN, c=24  | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---

\*>48h - time above 48h is not acceptable
