.. dcor documentation master file, created by
   sphinx-quickstart on Thu Sep 14 14:53:09 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

dcor version |version|
======================

|tests| |docs| |coverage| |pypi| |conda| |zenodo|

Distance covariance and distance correlation are
dependency measures between random vectors introduced in :cite:`a-distance_correlation`.

This package provide functions for calculating several statistics
related with distance covariance and distance correlation, including
biased and unbiased estimators of both dependency measures.

Input shapes
------------

For :func:`dcor.distance_correlation`, pass one- or two-dimensional arrays.
The first axis contains paired observations; a second axis contains the
components of each random vector. Thus ``x`` and ``y`` may have shapes
``(n, p)`` and ``(n, q)``, with different numbers of components but the same
number of observations. Shape ``(n,)`` represents a scalar random variable.

Random vectors may have an arbitrary number of components, but this does not
mean that arbitrary-rank tensors or batch axes are accepted. For example,
an input with shape ``(n, 2, 5)`` can be reshaped to ``(n, 10)`` if the last
two axes jointly describe the features of each observation. This computes
one dependence measure between random vectors, not separate correlations
for each tensor slice. See the :func:`dcor.distance_correlation` examples and
:func:`dcor.rowwise` for separate calculations over multiple datasets.

References
----------
.. bibliography:: refs.bib
   :labelprefix: A
   :keyprefix: a-

.. toctree::
   :hidden:
   :maxdepth: 4
   :caption: Contents:

   installation
   theory
   auto_examples/index
   apilist
   energycomparison
   Release Notes <https://github.com/vnmabus/dcor/releases>
   citing
   development
   contributors

dcor is developed `on Github <http://github.com/vnmabus/dcor>`_. Please
report `issues <https://github.com/vnmabus/dcor/issues>`_ there as well.

.. |tests| image:: https://github.com/vnmabus/dcor/actions/workflows/main.yml/badge.svg
    :alt: Tests
    :target: https://github.com/vnmabus/dcor/actions/workflows/main.yml

.. |docs| image:: https://readthedocs.org/projects/dcor/badge/?version=latest
    :alt: Documentation Status
    :target: https://dcor.readthedocs.io/en/latest/?badge=latest
    
.. |coverage| image:: http://codecov.io/github/vnmabus/dcor/coverage.svg?branch=develop
    :alt: Coverage Status
    :target: https://codecov.io/gh/vnmabus/dcor/branch/develop
    
.. |pypi| image:: https://badge.fury.io/py/dcor.svg
    :alt: Pypi version
    :target: https://pypi.python.org/pypi/dcor/
    
.. |conda| image:: https://img.shields.io/conda/vn/conda-forge/dcor
    :alt: Available in Conda
    :target: https://anaconda.org/conda-forge/dcor
    
.. |zenodo| image:: https://zenodo.org/badge/DOI/10.5281/zenodo.3468124.svg
    :alt: Zenodo DOI
    :target: https://doi.org/10.5281/zenodo.3468124
