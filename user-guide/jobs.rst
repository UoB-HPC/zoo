Running jobs
============

The Zoo using a PBSPro scheduling system to manage the diverse compute resources.

Using the queue
---------------

If you are unfamiliar with using a PBS queue, `this tutorial`_ may be useful.

.. _this tutorial: https://learn.scientificprogramming.io/learn-to-use-pbs-pro-job-scheduler-ffd9c0ad680d

Selecting nodes
---------------

The following must be added to your batch script or interative ``qsub`` command to ensure the job is started on the correct architecture.

+--------------------------+---------------+--------------+---------------------------------------------+
| Device                   | Class         | Architecture | Queue command                               |
+==========================+===============+==============+=============================================+
| NVIDIA GTX 1080 Ti       | Consumer GPU  | Pascal       | ``-lselect=1:ngpus=1:gputype=gtx1080ti``    |
+--------------------------+---------------+--------------+---------------------------------------------+
| NVIDIA GTX 2080 Ti       | Consumer GPU  | Turing       | ``-lselect=1:ngpus=1:gputype=gtx2080ti``    |
+--------------------------+---------------+--------------+---------------------------------------------+
| AMD Radeon VII           | Consumer GPU  | Vega 20      | ``-lselect=1:ngpus=1:gputype=radeonvii``    |
+--------------------------+---------------+--------------+---------------------------------------------+
| Intel NUC (Iris Pro 580) | Embedded GPU  | Gen9         | ``-lselect=1:ngpus=1:gputype=irispro580``   |
+--------------------------+---------------+--------------+---------------------------------------------+
| NEC SX-Aurora            | Vector Engine | NEC SX       | ``-lselect=1:nacc=1:acctype=aurora``        |
+--------------------------+---------------+--------------+---------------------------------------------+
| Intel Skylake (12 core)  | Server CPU    | Skylake Gold | ``-lselect=1:ncpus=24:cputype=skylake6162`` |
+--------------------------+---------------+--------------+---------------------------------------------+

Additional nodes
----------------

The following devices can be made available, but are currently not configured.

+-------------------------+---------------+--------------+
| Device                  | Class         | Architecture |
+=========================+===============+==============+
| NVIDIA K20m             | HPC GPU       | Kepler       |
+-------------------------+---------------+--------------+
| NVIDIA K40m             | HPC GPU       | Kepler       |
+-------------------------+---------------+--------------+
| NVIDIA GTX 580          | Consumer GPU  | Fermi        |
+-------------------------+---------------+--------------+
| NVIDIA GTX 680          | Consumer GPU  | Kepler       |
+-------------------------+---------------+--------------+
| NVIDIA GTX 780 Ti       | Consumer GPU  | Kepler       |
+-------------------------+---------------+--------------+
| NVIDIA GTX 980 Ti       | Consumer GPU  | Maxwell      |
+-------------------------+---------------+--------------+
| NVIDIA GTX TITAN X      | Consumer GPU  | Pascal       |
+-------------------------+---------------+--------------+
| AMD S9150               | HPC GPU       | Hawaii       |
+-------------------------+---------------+--------------+
| AMD S10000              | HPC GPU       | Tahiti       |
+-------------------------+---------------+--------------+
| AMD HD7970              | Consumer GPU  | Tahiti       |
+-------------------------+---------------+--------------+
| AMD R9-295X2            | Consumer GPU  | Hawaii       |
+-------------------------+---------------+--------------+
| AMD R9-290X             | Consumer GPU  | Hawaii       |
+-------------------------+---------------+--------------+
| AMD Fury X              | Consumer GPU  | Fiji         |
+-------------------------+---------------+--------------+
| AMD RX 480              | Consumer GPU  | Polaris      |
+-------------------------+---------------+--------------+
| Intel Xeon E5-2697 v2   | Server CPU    | Ivy Bridge   |
+-------------------------+---------------+--------------+
| AMD A10-7850K Radeon R7 | APU           | Kaveri       |
+-------------------------+---------------+--------------+
| Intel Xeon Phi 7210     | MIC           | KNL          |
+-------------------------+---------------+--------------+
| NVIDIA Jetson TX1       | ARMv8         | Cortex-A57   |
+-------------------------+---------------+--------------+
| SoftIron Overdrive 1000 | ARMv8         | Cortex-A57   |
+-------------------------+---------------+--------------+
| Marvell ThunderX2       | ARMv8         | TX2          |
+-------------------------+---------------+--------------+




Queue configuration
-------------------

All jobs should be submitted to the default ``workq`` queue.



