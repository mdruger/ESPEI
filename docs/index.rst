.. ESPEI documentation master file, created by
   sphinx-quickstart on Sat Jun 24 22:30:49 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. |logo| image:: _static/ESPEI-logo.png
          :height: 30pt
          :width: 30pt
          :alt: Logo

============
|logo| ESPEI
============

.. raw:: latex

   \part{Introduction}

.. toctree::
   :maxdepth: 1

   self
   installation
   quickstart


ESPEI, or Extensible Self-optimizing Phase Equilibria Infrastructure, is a tool for automated thermodynamic database development within the CALPHAD method. It uses `pycalphad`_ for calculating Gibbs free energies of thermodynamic models.


.. _pycalphad-fitting: https://github.com/richardotis/pycalphad-fitting
.. _pycalphad: http://pycalphad.org
.. _Richard Otis's thesis: https://etda.libraries.psu.edu/catalog/s1784k73d
.. _Jom 69, (2017): http://dx.doi.org/10.1007/s11837-017-2318-6
.. _Magnes. Technol. 2010 617-622 (2010): http://www.phases.psu.edu/wp-content/uploads/2010-Shang-Shunli-MagTech-ESPEI-0617-1.pdf


.. figure:: _static/cu-mg-mcmc-phase-diagram.png
    :alt: Cu-Mg phase diagram
    :scale: 100%

    Cu-Mg phase diagram from a database created with and optimized by ESPEI.
    See the :ref:`Cu-Mg Example`.



Goals
-----

1. Offer a free and open-source tool for users to develop multicomponent databases with quantified uncertainty
2. Enable development of CALPHAD-type models for Gibbs energy, thermodynamic or kinetic properties
3. Provide a platform to build and apply novel model selection and optimization methods

The implementation for ESPEI involves first fitting single-phase data by calculating parameters in thermodynamic models that are linearly described by the single-phase input data.
Then Markov Chain Monte Carlo (MCMC) is used to optimize the candidate models from the single-phase fitting to multi-phase zero-phase fraction data.
The benefit of this approach is the automated, simultaneous fitting for many parameters that yields uncertainty quantification, as shown in Otis and Liu High-Throughput Thermodynamic Modeling and Uncertainty Quantification for ICME. `Jom 69, (2017)`_.
Single-phase and multi-phase fitting methods are described in Chapter 3 of `Richard Otis's thesis`_.


History
-------

The ESPEI package is based on a fork of `pycalphad-fitting`_. The name and idea of ESPEI are originally based off of Shang, Wang, and Liu, ESPEI: Extensible, Self-optimizing Phase Equilibrium Infrastructure for Magnesium Alloys `Magnes. Technol. 2010 617-622 (2010)`_.

Change log
----------

.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: What's new

   CHANGES

See `what's new <CHANGES.html>`_!


.. raw:: latex

   \part{Tutorials}

.. toctree::
   :maxdepth: 1
   :caption: Tutorials


   cu-mg-example
   input_data


.. raw:: latex

   \part{Reference}

.. toctree::
   :maxdepth: 1
   :caption: Reference

   writing_input
   specifying_priors
   theory
   recipes
   advanced_schedulers
   api/modules


.. raw:: latex

   \part{Developer}

.. toctree::
   :maxdepth: 1
   :caption: Developer

   contributing
   design


.. raw:: latex

   \part{Appendix}

.. raw:: latex

   \chapter{Appendices}

Getting Help
============

For help on installing and using ESPEI, please join the `PhasesResearchLab/ESPEI Gitter room <https://gitter.im/PhasesResearchLab/ESPEI>`_.

Bugs and software issues should be reported on `GitHub <https://github.com/PhasesResearchLab/ESPEI/issues>`_.


License
=======

ESPEI is MIT licensed.

.. code-block:: none

   The MIT License (MIT)

   Copyright (c) 2015-2018 Richard Otis
   Copyright (c) 2017-2018 Brandon Bocklund
   Copyright (c) 2018-2019 Materials Genome Foundation

   Permission is hereby granted, free of charge, to any person obtaining a copy
   of this software and associated documentation files (the "Software"), to deal
   in the Software without restriction, including without limitation the rights
   to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
   copies of the Software, and to permit persons to whom the Software is
   furnished to do so, subject to the following conditions:

   The above copyright notice and this permission notice shall be included in all
   copies or substantial portions of the Software.

   THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
   IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
   FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
   AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
   LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
   OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
   SOFTWARE.


Citing ESPEI
============

If you use ESPEI for work presented in a publication, we ask that you cite the following publication::

   B. Bocklund, R. Otis, A. Egorov, A. Obaied, I. Roslyakova, Z.-K. Liu, ESPEI for efficient thermodynamic database development, modification, and uncertainty quantification: application to Cu-Mg, (2019). http://arxiv.org/abs/1902.01269.

   @article{Bocklund2019ESPEI,
   abstract = {The software package ESPEI has been developed for efficient evaluation of thermodynamic model parameters within the CALPHAD method. ESPEI uses a linear fitting strategy to parameterize Gibbs energy functions of single phases based on their thermochemical data and refine the model parameters using phase equilibrium data through Bayesian optimization within a Markov Chain Monte Carlo machine learning approach. In this paper, the methodologies employed in ESPEI are discussed in detail and demonstrated for the Cu-Mg system down to 0 K using unary descriptions based on segmented regression. The model parameter uncertainties are quantified and propagated to the Gibbs energy functions.},
   archivePrefix = {arXiv},
   arxivId = {1902.01269},
   author = {Bocklund, Brandon and Otis, Richard and Egorov, Aleksei and Obaied, Abdulmonem and Roslyakova, Irina and Liu, Zi-Kui},
   eprint = {1902.01269},
   month = {feb},
   title = {{ESPEI for efficient thermodynamic database development, modification, and uncertainty quantification: application to Cu-Mg}},
   url = {http://arxiv.org/abs/1902.01269},
   year = {2019}
   }


.. only:: html

   Indices and tables
   ==================

   * :ref:`genindex`
   * :ref:`modindex`
   * :ref:`search`
