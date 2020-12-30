hipSYCL
=======

hipSYCL_ is a implementation of SYCL 1.2.1 to run on AMD and NVIDIA GPUs built on top of AMD HIP (which itself allows targetting NVIDIA and AMD GPUs).
It is available on the zoo in the module ``hipsycl/0.8.1-prerelease``.

.. _hipSYCL: https://github.com/illuhad/hipSYCL


Building for AMD GPUs
---------------------

.. code-block:: bash

  syclcc-clang -std=c++14 -O3 --hipsycl-gpu-arch=gfx906 --hipsycl-platform=rocm  *.cpp

The ``gpu-arch`` flag should be set to the following for the AMD GPUs in the Zoo:

+------------+-------------+
| GPU        | Flag option |
+============+=============+
| Radeon VII | ``gfx906``  |
+------------+-------------+

Building for NVIDIA GPUs
------------------------

First load the cuda module: ``module load cuda/10.1``

.. code-block:: bash

  syclcc-clang -std=c++14 -O3 --hipsycl-gpu-arch=sm_60 --hipsycl-platform=cuda  *.cpp

The ``gpu-arch`` flag should be set to the following for the AMD GPUs in the Zoo:

+------------+-------------+
| GPU        | Flag option |
+============+=============+
| 2080 Ti    | ``sm_75``   |
+------------+-------------+
| 1080 Ti    | ``sm_61``   |
+------------+-------------+

