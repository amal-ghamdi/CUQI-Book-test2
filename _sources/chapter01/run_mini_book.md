
# Running the mini-book code examples


Here we suggest the following options to run the code notebooks in this mini-book:

- Running on your local machine (preferred)
- Running using the launch buttons (for quick exploration)

## Option 1: Running on your local machine (preferred)


To run the notebooks on your local machine, you will first need to install CUQIpy and its dependencies. CUQIpy installation instructions can be found [here](https://cuqi-dtu.github.io/CUQIpy/user/getting_started.html).

You can then download each notebook by clicking on the download button at the  top-right corner of the notebook, and run it on your local machine.

An alternative to using the download button, you can clone the book repository and run the notebooks on your local machine. To clone it using command line tools, run the following command inside the directory where you want to clone the repository:
```bash
git clone https://github.com/CUQI-DTU/CUQI-Book.git
```


## Option 2: Running using the launch button (for quick exploration)
You can run the notebooks using the launch button (a "rocket" icon at the top-right corner of each notebook) which gives you two options:
- Live Code: For running the notebook interactively using [Binder service](mybinder.org).
- Colab: For running the notebook on [Google Colab](https://colab.research.google.com/). 

Click on the option that you prefer.

### Notes:

- The Binder service may take a few minutes to set up the environment.
- On google colab, you may need to install CUQIpy by running the following command in a cell:
```python
!pip install cuqipy
```
