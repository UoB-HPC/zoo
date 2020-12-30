Intel OpenCL Intercept Layer
============================

The OpenCL Intercept Layer is a tool from Intel that can provide profiling information about kernel execution and OpenCL host API calls.

Generate a timeline
-------------------
Example usage is shown below. The results are placed in a file in ``~/CLIntercept_Dump``.


.. code-block:: bash

  module load intel/opencl-intercept-layer/39e6f56
  LD_PRELOAD=/nfs/software/x86_64/intel/opencl-intercept-layer/lib64/libOpenCL.so CLI_ChromeCallLogging=1 CLI_ChromePerformanceTiming=1 CLI_DllName=/nfs/software/x86_64/cuda/10.1/lib64/libOpenCL.so ./a.out

To view the timeline, open Chrome locally and nativate to ``chrome://tracing/`` then load the generated ``.json`` file.

