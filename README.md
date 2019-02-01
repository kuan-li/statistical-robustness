# "A Statistical Approach to Assessing Neural Network Robustness"

Here you can find a [PyTorch](http://pytorch.org/) implementation of [Adaptive Multilevel splitting](http://www.nowozin.net/sebastian/blog/multilevel-splitting.html) and code to reproduce the experiments in [our paper](https://arxiv.org/abs/1811.07209), to appear at the 7th International Conference on Representation Learning (ICLR 2019).

## Instructions

To run Experiment 6.2:

1. Install the Python package `seaborn`, and the latest versions of `NumPy`/`PyTorch`.
2. Install [Gurobi](https://www.gurobi.com). (This is required for the PLNN package to load, but is not actually used by the core code itself.)
3. Activate Gurobi license.
4. From the base directory:
	* `python -m exp_6_2.process_data`
	* `python -m exp_6_2.run_exp`
	* `python -m exp_6_2.plot_exp`

To run Experiment 6.3:

1. Install the packages as for Exp 6.2.
2. From the base directory:
	* `python -m exp_6_3_mnist.train`
	* `python -m exp_6_3_mnist.run_baseline`
	* `python -m exp_6_3_mnist.run_exp`
	* `python -m exp_6_3_mnist.plot_exp`

## Pertinent files

* `/exp_6_2`
	* `plot_exp.py` Produces Figures 1 and 4 from the paper for Experiment 6.2.
	* `process_data.py` Converts the CollisionDetection property files into pickled objects and a summary file. Also produces naive MC estimates.
	* `run_exp.py` Runs AMLS on the 500 properties to produce results for Experiment 6.1 and 6.2.
* `/exp_6_3_mnist`
	* `plot_exp.py` Produces the MNIST panel of Figure 2.
	* `run_baseline.py` Produces naive MC estimates of adversarial properties of varying rareness.
	* `run_exp.py` Runs AMLS on adversarial properties varying the hyperparameters to produce results for Ex 6.3.
	* `train.py` Trains the simple feedforward classifier on MNIST.
* `/plnn` A modified version of the [PLNN package](https://github.com/oval-group/PLNN-verification) with some bug fixes for the latest PyTorch.

## Notes

* The experiment of sections 6.2 in the paper is currently available. Please contact me if you would like to obtain the code for Section 6.1.
* The code to run the experiments was not completely rerun due to the need for computational resources, so contact me if you are having trouble with them.
* You may wish to modify the code to run the experiments so that it runs different values in parallel across multiple GPUs.

## TODO

* Experiment code for Section 6.3.
* Experiment code for Section 6.4.