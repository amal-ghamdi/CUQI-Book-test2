# User showcase collection

The [CUQIpy User Showcase repository](https://github.com/CUQI-DTU/CUQIpy-User-Showcase) is a dedicated space for collecting and sharing a diverse array of practical applications built using CUQIpy. The repository originated as a community-driven initiative where enthusiastic CUQIpy users generously contribute their own use cases, custom implementations, and experiments. Its main purpose is to serve as an educational and practical resource, providing real-world examples of how CUQIpy can be used to solve complex inverse problems and quantify uncertainty across different domains.

The repository houses a wide variety of solved problems, demonstrating the flexibility of CUQIpy. Examples include 1D and 2D deblurring/deconvolution (utilizing [Besov priors](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/001_Besov_2D_deblurring/Besov_2D_deblurring.ipynb), [implicit priors](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/005_Implicit_Regularized_Gaussian/implicit_priors.ipynb), and [smoothed Laplace](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/007_smoothed_Laplace/smoothed_laplace.ipynb) methods), [fusion plasma tomography](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/011_fusion_plasma_tomography/Fast-ion_distribution_reconstruction_notebook.ipynb), [super-resolution imaging](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/012_super_resolution/STORM.ipynb), and physical system modeling like [spring systems](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/010_spring_system/spring.ipynb) and [inverse Robin boundary](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/009_inverse_Robin/robin.ipynb) problems. Users have also contributed examples that showcase advanced techniques such as [plug-and-play priors](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/006_plug_and_play_prior/pnp_prior.ipynb) (combining neural network denoisers with Bayesian inference), [delayed acceptance with ODEs](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/008_delayed_acceptance/da_with_ode.ipynb), [dimension-reduction with Laplace priors](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/013_certified_coordinate_selection/ccs_wavelets.ipynb), and creating [custom forward models](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/002_eigenvalue_forward/eigenvalue_forward.ipynb) and [samplers](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/008_delayed_acceptance/da_with_ode.ipynb).

For example in the [super-resolution imaging](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/blob/main/012_super_resolution/STORM.ipynb) case study contributed by Rafael Flock, a novel method is proposed to perform uncertainty quantification for stochastic optical reconstruction microscopy (STORM). STORM, shown in Figure 1, is a super-resolution microscopy method based on single-molecule stochastic switching, where the goal is to detect molecule positions in live cell imaging. The noisy image is obtained by a microscope detecting the photon count of the (fluorescence) photoactivated molecules.

<figure>
<img src="figures/storm_data.png" alt="Storm data" width="600"/>
<figcaption>Figure 1. Ground truth and noisy data in a STORM problem. The goal is infer the location of molecules (white points in the left plot) from the noisy data shown in the right plot.
</figcaption>
</figure>

For the STORM problem, Laplace priors are an appealing choice for their ability to promote sparsity and handle heavy-tailed distributions, but their application in high-dimensional inverse problems is challenging. This case study proposes a novel approach that combines the method of Certified Coordinate Selection (CCS) with a gradient-based sampling method. CCS allows one to efficiently identify the components in the unknown parameters that contribute most to the update from the prior to the posterior, effectively reducing the dimensionality of the problem considered during inference, as shown in Figure 2.

<figure>
<img src="figures/storm_ccs.png" alt="Storm data" width="300"/>
<figcaption>Figure 2. The selected coordinates after CCS are illustrated as black pixels and the exact locations of the molecules as red.
</figcaption>
</figure>

The CUQIpy developer team highly encourages new submissions and a [detailed instruction](https://github.com/CUQI-DTU/CUQIpy-User-Showcase/tree/main?tab=readme-ov-file#contribution-guidelines) on how to contribute is available at the User Showcase GitHub repository.

## Resources
- User-Showcase GitHub repository: https://github.com/CUQI-DTU/CUQIpy-User-Showcase