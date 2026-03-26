#  CUQIpy Benchmarks

To understand performance of different UQ methods and implementations for Bayesian inverse problems, CUQI project graduate interns Tania Andreea Goia and Naoki Sakai built a library of CUQIpy benchmarks that researchers and students can use to test MCMC and optimization methods on.

The library includes a collection of benchmark problems, including linear and nonlinear inverse problems, and varying priors and likelihoods choices. Some of these benchmarks are essentially a density function not necessarily stemming from an inverse problem, but still useful for testing sampling methods. Examples include the [donut](https://github.com/CUQI-DTU/CUQIpy-Benchmarks/blob/main/demos/D01-donut.ipynb), the [banana](https://github.com/CUQI-DTU/CUQIpy-Benchmarks/blob/main/demos/D02-banana.ipynb), and the [sixmodal](https://github.com/CUQI-DTU/CUQIpy-Benchmarks/blob/main/demos/D03-sixmodal.ipynb) density functions. The library also includes actual inverse problems, such as a [2D simple linear inverse problem](https://github.com/CUQI-DTU/CUQIpy-Benchmarks/blob/main/demos/D04-simplest-bip.ipynb), a [heat equation-based problem](https://github.com/CUQI-DTU/CUQIpy-Benchmarks/blob/main/demos/D05-heatstep.ipynb), and a [Poisson equation-based problem](https://github.com/CUQI-DTU/CUQIpy-Benchmarks/blob/main/demos/D06-poisson.ipynb). 

 The benchmarks are designed to be easy to use and extend, with utilities methods that simplifies applying different sampling methods with different settings, visualize, and summarize results.

 An example of how to use the benchmarks is shown below, where we compare the performance of different MCMC methods on the sixmodal density function benchmark. Note that we use modules `benchmarksClass` and `utilities` that are part of the benchmarks library, which provides utilities for setting up the benchmark problems, running sampling methods, and visualizing results.

 For setup:
 ```python
 target_sixmodal = benchmarksClass.Sixmodal()
 samples = utilities.MCMCComparison(
    target_sixmodal,
    scale = [1,1,0.1,0.3,0.05],
    Ns = [8500,8500,8500,8500,850],
    Nb = [1500,1500,1500,1500,150],
    x0 = np.array([1,2]),
    seed = 12,
    chains=1,
    selected_criteria= ["ESS", "AR", "LogPDF", "Gradient","Rhat"],
    selected_methods =["MH_fixed", "CWMH", "ULA", "MALA", "NUTS"])
 ```
 Then, we can create comparison plots and tables of sampling methods parameters and  MCMC diagnostics with the following code:
 ```python
 samples.create_comparison()
 samples.create_plt()
 ```
 | Metric          | MH      | CWMH   | ULA    | MALA   | NUTS   |
|-----------------|---------|--------|--------|--------|--------|
| samples         | 8500    | 8500   | 8500   | 8500   | 8500   |
| burnins         | 1500    | 1500   | 1500   | 1500   | 1500   |
| scale           | 1.0     | 1.0    | 0.065  | 0.5    | -      |
| ESS(v0)         | 190.945 | 46.069 | 34.643 | 91.406 | 868.884|
| ESS(v1)         | 245.282 | 62.05  | 61.713 | 256.58 | 344.878|
| AR              | 0.374   | 0.615  | 1.0    | 0.512  | 0.911  |
| LogPDF          | 10002   | 20002  | 10002  | 10002  | 80520  |
| Gradient        | 0       | 0      | 10002  | 10002  | 80520  |
| Rhat(v0)        | 1.008   | 1.035  | 1.006  | 1.013  | 1.002  |
| Rhat(v1)        | 1.0     | 1.027  | 1.001  | 1.006  | 1.003  |
| LogPDF/ESS      | 45.857  | 369.999| 207.606| 57.485 | 132.678|
| Gradient/ESS    | 0.0     | 0.0    | 207.606| 57.485 | 132.678|

 
 <figure>
<img src="figures/banana.png" alt="figure" width="600"/>
<figcaption>Figure 1. Results for sampling the banana-shaped density function benchmark using different MCMC methods.
</figcaption>
</figure>






## Resources
- Benchmarks GitHub repository: https://github.com/CUQI-DTU/CUQIpy-Benchmarks