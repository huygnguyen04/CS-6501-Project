# CS-6501-Project
Research Project for CS 6501

## Overview 
This project aims to research and optimize GPU L2 cache performance using GPGPU-Sim. 

## Updates
- Review related literature
- Setting up the GPGPU Simulation on the UVA GPU Server
- Compiling and running some basic CUDA codes (vector add, matrix mul)
- Try using the Rodinia benchmark with GPGPU Sim

# Problems
- Cannot seem to get the metrics for GPGPU-Sim and some necessary package are missing from the portal (need to download manually)
- May use Ubuntu VM to see if it is better

## Specific Steps and Setup

- **Literature Review and Environment Setup**
   ```bash
   module load cuda/11.7.0 # load the cuda version 
   which nvcc # find the location of nvcc to set the path for CUDA_INSTALL_PATH

   export CUDA_INSTALL_PATH=/sw/ubuntu2204/ebu082024/software/common/core/cuda/11.7.0/ # set the path

   git clone https://github.com/gpgpu-sim/gpgpu-sim_distribution.git # clone the gpgpu sim

   source setup_environment release #
   ```

- **Compiling and Running a CUDA Benchmark**
  - Developed a simple matrix multiplication CUDA program (`mmul.cu` and `matmul.cu`) as a benchmark.
  - Compiled the program with the following command to link with the simulated CUDA runtime:
    ```bash
    nvcc --cudart shared -o mmul mmul.cu
    ```
  - Ran the benchmark using:
    ```bash
    ./mmul
    ```
  - The benchmark ran successfully (output: "COMPLETED SUCCESSFULLY") confirming the basic simulation setup.
  - Plan for using Rodinia benchmark - in progress

## Future Plans
- **Switch Environment:**  
  Transition to an Ubuntu-based system for greater control over software dependencies and modules.
- **Benchmark Expansion:**  
  Clone and compile the Rodinia benchmark suite to run a wider range of applications and obtain richer simulation data.
- **Detailed Metrics Collection:**  
  Further tweak configuration settings to reliably output detailed L2 cache statistics and overall simulation metrics.
- **Seek Assistance:**  
  Contact the CS help desk if necessary for module support and configuration issues, and seek guidance on best practices for extracting simulation statistics.

## How to Run (Summary)
1. **Set up Environment Variables:**
   ```bash
   export CUDA_INSTALL_PATH=/usr/local/cuda
   export CONFIG=GTX480
   export GPUAPPS_ROOT=~/gpuapps # fix this
   export GPGPUSIM_CONFIG=$(pwd)/gpgpusim.config
   ```

2. **Load necessary module on the portal**
   ```bash
   module load cuda/11.7.0
   
   which nvcc 

   export CUDA_INSTALL_PATH=/sw/ubuntu2204/ebu082024/software/common/core/cuda/11.7.0/

   git clone 

   source setup_environment release
   ```

