# Integration of CUQIpy and UM-Bridge

In this book, we demonstrated that CUQIpy is a comprehensive and accessible software tool for Uncertainty Quantification (UQ) in inverse problems via presenting multiple examples and highlighting CUQIpy-based research projects. In an effort to make CUQIpy interoperable with the UQ software ecosystem,  we have integrated the CUQIpy library with [UM-Bridge](https://um-bridge-benchmarks.readthedocs.io/en/docs/) (the UQ and Model Bridge), a unified interface that links advanced models and simulations with UQ software. This integration allows users to leverage CUQIpy's powerful methods and models alongside other libraries to solve a wide range of UQ problems.

## What is UM-Bridge?
UM-Bridge is a software framework that provides a unified interface for connecting advanced models and simulations with UQ and optimization software. It relies on the HTTP protocol to enable communication between the model-side and method-side of the UQ workflow, defining a standard API for exchanging information between the two.

It allows seamless integration of models and UQ libraries, creating shareable containerized models and benchmarks, and scaling computations to supercomputers and cloud infrastructure with minimal effort. See Figure 1 for an illustration of the UM-Bridge framework.


```{figure} figures/umbridge.jpg
:label: FigureUmBridge
:alt: Figure UM-Bridge
:width: 600px
:align: center
The UM-Bridge framework, a unified interface for connecting advanced models and simulations with UQ and optimization software. Image credit: the [UM-Bridge documentation](https://um-bridge-benchmarks.readthedocs.io/en/docs/) and [@seelinger2025democratizing].
```

## CUQIpy-UMBridge plugin
We developed the [CUQIpy-UMBridge](https://github.com/CUQI-DTU/CUQIpy-UMBridge) plugin to seamlessly enable the use of CUQIpy within the UM-Bridge workflow. The plugin provides two main modules:
- `server`: allows CUQIpy Models and Distributions to be served as UM-Bridge  models, enabling their use in any UM-Bridge-compatible software and workflows.
- `client`: allows CUQIpy to communicate with UM-Bridge models and use them in CUQIpy workflows.


## Contributing to "democratizing uncertainty quantification"

As part of the UM-Bridge project, {cite}`seelinger2025democratizing` presented UM-Bridge as a tool for "democratizing uncertainty quantification". The paper presents the UM-Bridge framework and its capabilities, provides a list of UQ software tools that are compatible with UM-Bridge, including CUQIpy, and demonstrates how the UM-Bridge workflow can be used to solve UQ problems through several examples that serve as a benchmark collection. We contributed to the paper by providing the CUQIpy-UMBridge plugin and developing three benchmark examples that demonstrate the use of CUQIpy within the UM-Bridge framework. These examples are a [CT reconstruction problem](https://github.com/UM-Bridge/benchmarks/tree/main/benchmarks/cuqi-ct), a [deconvolution problem](https://github.com/UM-Bridge/benchmarks/tree/main/benchmarks/deconvolution-1d), and a [heat equation problem](https://github.com/UM-Bridge/benchmarks/tree/main/benchmarks/heat-1d). They demonstrate how to easily set up versatile, UM-Bridge-compatible benchmarks with CUQIpy.


The link to the paper benchmarks is provided in the resources section below.

## Resources
- Paper: {cite}`seelinger2025democratizing`
- Paper code GitHub repository (the benchmarks): https://github.com/UM-Bridge/benchmarks
- CUQIpy-UMBridge plugin GitHub repository: https://github.com/CUQI-DTU/CUQIpy-UMBridge