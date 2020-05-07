DPC++
=======

DPC++ is Intel implementation of SYCL 1.2.1 as part of oneAPI.

A lot of the development is on GitHub, and we install it from top of tree occasionally.

The latest version is in the `intel/oneapi/20200507` module.
Earlier versions are in the `intel/oneapi/beta` and `llvm/sycl` modules.


Building for Intel Xeon CPUs
----------------------------

.. code-block:: bash

   module load intel/opencl/experimental/2020.10.3.0.04
   module load intel/oneapi/20200507
   clang++ --gcc-toolchain=/nfs/software/x86_64/gcc/7.4.0 -std=c++11 -fsycl -lOpenCL <flags> *.cpp

   LD_PRELOAD=/nfs/software/x86_64/intel/opencl/2020.10.3.0.04/x64/libintelocl.so ./a.out

