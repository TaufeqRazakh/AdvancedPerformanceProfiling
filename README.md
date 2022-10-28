# Advanced Performance Profiling
CSCI 653: High Performance Computing and Simulations (Fall 2022)

## Pre-requisite: Installing the profiler and analysis GUI
+ Download & install the latest version of the Intel oneAPI Vtune Profiler GUI from [here](https://www.intel.com/content/www/us/en/developer/tools/oneapi/vtune-profiler-download.html).

+ Download & install the latest version of the Intel oneAPI Advisor GUI from [here](https://www.intel.com/content/www/us/en/developer/articles/tool/oneapi-standalone-components.html#advisor)

Upon installation, launch the GUI. Depending on your OS, the default installation path would be.
- windows: C:\Program Files (x86)\Intel\oneAPI\
- Linux OS: /opt/intel/oneapi/
- mac OS: /opt/intel/oneapi/

## Performance Profiling FMM Implementation

You are already familar with the  a fast algorithm for particle simulations, [Journal of Computational Physics 73,  325–
348 (1987)] introduced in assignment 2. VTune is capable of generatng reports for sereval analysis on the application target.

They are
+ performance-snapshot
+ hotspot analysis
+ anomaly-detection
+ memory-consumption
+ micro-architecture exploration
+ memory-access
+ hpc-performance
+ io
+ gpu-offload
+ gpu-hotpost
+ fpga-interactoin
+ system-overview
+ platform-profiler

We will carry out a hotspot analysis and try to understand our program by looking at the profiler report that's generated.

Request a compute node the command 
```
qsub -I
```
Run the Vtune hotspot analysis command
```
vtune --collect hotspots --result-dir rFMMHotspots ./fmm2d
```

With the profiling complete, we will now view the result
