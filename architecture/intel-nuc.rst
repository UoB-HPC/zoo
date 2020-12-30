Intel NUC
=========

 You will need to load the GPU driver
.. code-block:: bash

 $ module load intel/neo


 You should also check that the graphics driver does not have the "hang check" enabled which causes long running kernels to hang. The following file should contain ``N`` or ``0``:

.. code-block:: bash

 $ cat /sys/module/i915/parameters/enable_hangcheck
 N

Obsolete: If you would like to run on the Intel Iris Pro 580 integrated GPU in the NUC box, please contact us over email so that we may add the necessary group permissions.
