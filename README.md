## Generating Documentation Locally

The full documentation can be generated locally using the provided `Makefile`. Note that Windows users may need to install `make` before proceeding with the below steps. For convenience a yaml file is also included, which allows one to easily construct a conda environment. To create the conda environment using the yaml file and a terminal, first [download Anaconda](https://www.anaconda.com/). Once Anaconda has been installed the conda environment `rc-docs` can be created using
```
conda env create -f conda_dev_env.yml
```
This new environment can then be activated as follows
```
conda activate rc-docs
```

Using the `rc-docs` environment we can now easily generate the documentation locally using the following make command:
```
make html
```
this command builds the documentation and stores it in the directory `build`. 

One can then view the documentation using:
```
make view 
```
which will open the index page of the documentation. 

Although not necessary, one can then remove the build folder using:
```
make clean
```
