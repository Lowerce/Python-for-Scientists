# Python for Science

A curated list of recommended Python frameworks, libraries, software and
resources, all particularly useful for scientific Python users.

Intended for students and researchers in the sciences who want to get
the most out of the open-source Python ecosystem.

There is a section of [must-haves for beginners](#beginners-recommendations).

List inspired by [awesome-python](https://github.com/vinta/awesome-python),
which is a great similar resource for anything else you might want to do
with Python!

Some libraries appear multiple times where they are useful in multiple
ways.


- [Python-for-Science](#python-for-science)
    - [Algebra](#algebra)
    - [Animations](#animations)
    - [Bayesian Analysis](#bayesian-analysis)
    - [Code Quality](#code-quality)
    - [Data Storage](#data-storage)
    - [Dates and Times](#dates-and-times)
    - [Debugging](#debugging)
    - [Development Environments](#development-environments)
    - [Documentation](#documentation)
    - [Domain-specific](#domain-specific)
    - [Gotchas](#gotchas)
    - [GPU Acceleration](#gpu-acceleration)
    - [Graphical Interfaces](#graphical-interfaces)
    - [Job Scheduling](#job-scheduling)
    - [Labelled data](#labelled-data)
    - [Mathematical Library Functions](#mathematical-library-functions)
    - [Numerical Data](#numerical-data)
    - [Optimisation](#optimisation)
    - [Package Management](#package-management)
    - [Parallelization](#parallelization)
    - [Physical Units](#physical-units)
    - [Plotting](#plotting)
    - [Presentations](#presentations)
    - [Profiling and Benchmarking](#profiling-and-benchmarking)
    - [Speed](#speed)
    - [Statistics](#statistics)
    - [Testing](#testing)
    - [Visualisation](#visualisation)
    - [Workflow](#workflow)
- [Beginners Recommendations](#beginners-recommendations)


- - -


## Algebra

*Libraries for manipulation of symbolic algebra, analytic integration etc.*

* [SymPy]() -
* [sage]()


## Animations

* [animatplot]() -


## Bayesian Analysis

* [pymc]() -


## Code Quality

* [PEP8]() -
* [flake8]() -
* [pycodestyle]() -
* [structure](https://docs.python-guide.org/writing/structure/) - The officially recommended way to structure any python project.


## Data Storage

* [netcdf4]() -
* [xarray]() -
* [MITgcm]() -


## Dates and Times

* [dateutil](https://dateutil.readthedocs.io/en/stable/) - Provides powerful extensions to the standard datetime module available in Python.


## Debugging

* [pdb]() - Python debugger


## Development Environments

*Programs to write code into. The main choice is between a software-engineering style IDE, and one intended specifically for scientific users.*

* [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) - An IDE which incorporates Jupyter notebooks.
* [PyCharm](https://www.jetbrains.com/pycharm/) - Very powerful IDE for python. Use if you want the full powers a software engineer would expect.
Has a professional version, which is free for students.
* [spyder](https://www.spyder-ide.org/) - MatLab-like development environment for scientific python users.


## Documentation

* [sphinx]() -
* [nbconvert](https://nbconvert.readthedocs.io/en/latest/) - Convert jupyter notebooks to other formats such as PDF, LaTeX, HTML.


## Domain-specific

*Libraries of tools tools developed for python users in various fields of science.*

* [astropy]() -
* [Biopython](https://biopython.org/) - Tools for biological computation.
* [cartopy]() -
* [geoviews](http://geoviews.org/) - makes it easy to explore and visualize geographical, meteorological, and oceanographic datasets, such as those used in weather, climate, and remote sensing research.
* [MetPy](https://unidata.github.io/MetPy/latest/) - MetPy is a collection of tools in Python for reading, visualizing and performing calculations with weather data.
* [PlasmaPy]() -
* [psychopy]() -
* [pyrocko](https://pyrocko.org/) - A seismology toolkit for python.
* [SpectroscoPyx](https://github.com/PlasmaPy/SpectroscoPyx) - A community developed python package for spectroscopy.
* [TomoPy](https://tomopy.readthedocs.io/en/latest/) - Package for tomographic data processing and image reconstruction.


## Forecasting

* [prophet]() -


## Gotchas

* [python-gotchas]() -


## GPU acceleration

* [py-cuda]() -
* [numba]() -


## Graphical interfaces

* [pyqt5]() -


## Job scheduling

* [experi]() -
* [papermill](https://papermill.readthedocs.io/en/latest/) - A  tool for parameterizing, executing, and analyzing multiple Jupyter Notebooks.


## Labelled data

* [pandas]() -
* [xarray]() -


## Mathematical library functions

* [scipy](https://docs.scipy.org/doc/scipy/reference/) - The standard resource for all kinds of mathematical functions.
* [xrft](https://xrft.readthedocs.io/en/latest/) - Discrete Fourier transform operations for xarray data structures.


## Numerical data

* [numpy](http://www.numpy.org/) - The fundamental package for numerhon.
So ubiquitous that it might as well be part of python's standard library at this point.
Ultimately just a contiguous-in-memory C array, wrapped very nicely with python.


## Optimisation problems

* [nlopt]() -


## Package Management

*Keep track of module dependencies, python versions, and virtual environments.*

* [conda](https://conda.io/docs/index.html) - A package manager specifically intended for use by the scientific python community.
Developed by the authors of numpy to manage both python packages and the underlying C/Fortran libraries which make them fast.
Also obviates the need for system virtual environments.
* [anaconda](https://www.anaconda.com/) - Conda, but packaged with a wide range of useful scientific python libraries, including many from this list.
* [pip](https://pip.pypa.io/en/stable/) - The standard way to install python packages. Use when you can't use conda, but will play nicely together.
* [setuptools](https://setuptools.readthedocs.io/en/latest/) - For when you make your own module, and want to install it properly into your conda environment (so you never need to touch your `$PYTHONPATH`!)


## Parallelization

*Use all the cores of your machine, and scale up to clusters!*

* [dask](https://dask.org/) - Tools for splitting up computations and executing them across many processors in parallel.
[dask.array](http://docs.dask.org/en/latest/array.html) in particular provides a numpy-like interface to a chunked-in-memory array.
Dask is especially useful for analysing datasets which are larger than your RAM.
* [xarray](http://xarray.pydata.org/en/stable/) - Employs dask behind the scenes to parallelize most operations.
Simply load your dataset in "chunks" and xarray will operate on each chunk in parallel:
```python
# Load data in chunks
ds = open_dataset('data.nc', chunks={'space': 100}

# Will operate on each spatial chunk in parallel using dask
ds['density'].mean(dim='time')
```


## Physical Units

* [pint]() -
* [astropy.units]()


## Plotting

*Producing static plots of publication quality.*

* [matplotlib]() -
* [anatomy of matplotlib](https://github.com/matplotlib/AnatomyOfMatplotlib) - Tutorial on how matplotlib is structured.
* [scientific-matplotlib]() -
* [seaborn]() -
* [xarray.plot]() -
* [colorcet](http://colorcet.pyviz.org/) - A set of useful [perceptually uniform](https://arxiv.org/abs/1509.03700) colormaps for plotting scientific data


## Presentations and sharing work

* [RISE]() -
* [Binder](https://mybinder.org/) - Online Jupyter Notebook hosting for GitHub repositories.
Allows users to run Jupyter notebooks from GitHub repositories in the cloud, without Python installed locally.
* [jupyter-rise]() -
* [nb_pdf_template]() -


## Profiling and benchmarking

* [py-spy](https://github.com/benfred/py-spy) - A profiler for python code which doesn't interfere with the running process.


## Speed

*Python inevitably sacrifices some speed to gain increased clarity.
Scientific programs usually have one or two functions which do 90% of the work, and there are various ways to dramatically speed these up.
Use in conjunction with parallelization through dask if you want as much speed as possible.*

* [cython](https://cython.org/) - A compiler which allows you to write snippets of C code into your python for massive speed increases.
* [F2PY](https://docs.scipy.org/doc/numpy/f2py/) - For calling fast, compiled Fortran subroutines from Python (part of SciPy)
* [numba](https://numba.pydata.org/) - *Automatic* generation of fast compiled C code from Python functions.
* [bottleneck](https://kwgoodman.github.io/bottleneck-doc/) - A collection of fast numpy array functions written in C.
* [Theano](http://www.deeplearning.net/software/theano/) - Allows you to define, optimize, and evaluate mathematical expressions involving multi-dimensional arrays efficiently.


## Statistics

* [statsmodels](http://www.statsmodels.org/stable/index.html) - Provides classes and functions for the estimation of many different statistical models, as well as for conducting statistical tests, and statistical data exploration.


## Testing

*Check that your code actually does what you think it will do!*

* [pytest](https://docs.pytest.org/en/latest/) - The standard unit testing framework for python.
Essential - if you're not unit-testing your calculations then you are merely hoping that they are actually doing what you think they are.
`pytest` does a lot of magic behind the scenes to make it as simple as possible to use, with no boilerplate.
* [pytest-clarity](https://github.com/darrenburns/pytest-clarity) - A plugin which improves the readability of pytest output.
* [hypothesis](https://hypothesis.readthedocs.io/en/latest/) - Hypothesis testing for python.
Normal tests check that your function behaves as expected for some specific input.
Hypothesis tests check that your function behaves as expected for any input of some type, e.g. any string, or [any numpy array](https://hypothesis.readthedocs.io/en/latest/numpy.html).
Basically magic, compatible with pytest, and the algorithms used in the implementation are very interesting.
* [cosmic-ray](https://cosmic-ray.readthedocs.io/en/latest/) - Mutation testing in python. Checks that your test coverage is robust by randomly changing pieces of your code and checking that this change is actually caught by a test failing.
* [flaky](https://pypi.org/project/flaky/) - pytest plugin for automatically re-running inconsistent ("flaky") tests.


## Visualisation

* [animatplot]() -
* [mayavi]() -
* [cartopy]()
* [bokeh]() -
* [plotly]() -
* [holoviews]() -


## Workflow

*Don't just write and run python scripts. Tools to make your workflow faster, clearer, and easier to come back to later.    *

* [ipython](https://ipython.readthedocs.io/en/stable/) - Run python interactively, like MatLab! Forms the backend of jupyter notebooks.
* [jupyter notebooks](https://jupyter.org/) -
* [jupyterlab](https://jupyterlab.readthedocs.io/en/stable/) - A development environment in which you can write Jupyter notebooks.
The spiritual successor to spyder, in that it is designed specifically for scientists.
* [papermill](https://papermill.readthedocs.io/en/latest/) - A  tool for parameterizing, executing, and analyzing multiple Jupyter Notebooks.


# Beginner Recommendations

* First, install python through anaconda, which will also give you the packages you're about to use.
* Write your code in either `pycharm` (if you want a professional IDE), `spyder` or  `jupyterlab` (if you're used to MatLabs' environment).
* Become familiar with `numpy`, the fundamental numeric object in python, and `matplotlib`, the standard way to plot.
* Next, wrap your data into clearer, higher-level objects with either `Pandas` or `xarray` (use `xarray` if your data has more than one dimension).
* Before writing new analysis functions, check if someone has already solved your problem for you in `scipy` , or in one of python's domain-specific scientific software packages.
* As soon as you start writing your own analysis functions, test they're correct with unit tests written with `pytest`.
* Analyse your data interactively with `ipython`, and record your work in a `jupyter notebook`.
