Running jobs
============

The Zoo using a PBSPro scheduling system to manage the diverse compute resources.

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

Queue configuration
-------------------

All jobs should be submitted to the default ``workq`` queue.



.. |NVIDIA K20m             | HPC GPU       | Kepler       | `-lnodes=1:gpus=1:k20`       |
   | NVIDIA K40m             | HPC GPU       | Kepler       | `-lnodes=1:gpus=1:k40`       |
   | NVIDIA GTX 580          | Consumer GPU  | Fermi        | `-lnodes=1:gpus=1:gtx580`    |
   | NVIDIA GTX 680          | Consumer GPU  | Kepler       | `-lnodes=1:gpus=1:gtx680`    |
   | NVIDIA GTX 780 Ti       | Consumer GPU  | Kepler       | `-lnodes=1:gpus=1:gtx780ti`  |
   | NVIDIA GTX 980 Ti       | Consumer GPU  | Maxwell      | `-lnodes=1:gpus=1:gtx980ti`  |
   | NVIDIA GTX 1080 Ti      | Consumer GPU  | Pascal       | `-lnodes=1:gpus=1:gtx1080ti` |
   | NVIDIA GTX TITAN X      | Consumer GPU  | Pascal       | `-lnodes=1:gpus=1:titanx`    |
   | AMD S9150               | HPC GPU       | Hawaii       | `-lnodes=1:gpus=1:s9150`     |
   | AMD S10000              | HPC GPU       | Tahiti       | Unavailable                  |
   | AMD HD7970              | Consumer GPU  | Tahiti       | `-lnodes=1:gpus=1:hd7970`    |
   | AMD R9-295X2            | Consumer GPU  | Hawaii       | `-lnodes=1:gpus=1:r9-295x2`  |
   | AMD R9-290X             | Consumer GPU  | Hawaii       | `-lnodes=1:gpus=1:r9-290x`   |
   | AMD Fury X              | Consumer GPU  | Fiji         | `-lnodes=1:gpus=1:furyx`     |
   | AMD RX 480              | Consumer GPU  | Polaris      | `-lnodes=1:gpus=1:rx480`     |
   | Intel Xeon E5-2697 v2   | Server CPU    | Ivy Bridge   | `-lnodes=1:ppn=24:ivybridge` |
   | AMD A10-7850K Radeon R7 | APU           | Kaveri       | `-lnodes=1:kaveri`           |
   | Intel Xeon Phi 7210     | MIC           | KNL          | `-lnodes=1:ppn=256:knl`      |
   | NVIDIA Jetson TX1       | ARMv8         | Cortex-A57   | `-lnodes=1:ppn=4:jetson`     |
   | SoftIron Overdrive 1000 | ARMv8         | Cortex-A57   | `-lnodes=1:ppn=4:overdrive`  |

