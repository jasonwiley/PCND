PCND on Volta (V100)

Prebuilt Singularity container and example job script for running PCND (HOOMD-based simulations) on LONI clusters with NVIDIA Tesla V100 (Volta) GPUs.

For A100 GPUs, use the container in the a100/ folder instead.

Getting the container

The container is too large to store in the repository, so it is attached to the Releases page (right side of the repository page). Download PCND_volta.sif, then copy it to the cluster:

scp PCND_volta.sif YOUR_USERNAME@CLUSTER_HOSTNAME:/work/YOUR_USERNAME/

After downloading, check that the file is intact by comparing its checksum with the one listed below:

sha256sum PCND_volta.sif
Cluster details
GPUs: 2x Tesla V100-PCIE-32GB
NVIDIA driver: 580.105.08 (supports up to CUDA 13.0)
OS: Red Hat Enterprise Linux 8.10
Container runtime: singularity-ce 4.3.5
Container details
File: PCND_volta.sif
Size: 1.8 GB
SHA-256: 578638300919028bff00f241062189d88fd32b2d5adfea67517d7155d3c5ee8a
Ubuntu 20.04 base
Conda environment PCND (from conda-forge): Python 3.7, NumPy 1.14.6, CUDA toolkit 9.2
Prebuilt HOOMD at /hoomd/lib/python
Running a job

An example Slurm job script is included in this folder. Before using it, replace the placeholders for your allocation, email address, container path, and job folders, then submit it with sbatch.

Notes
The container definition file copies in a prebuilt PCND_install folder from the author's machine, which is not included in this repository. Use the prebuilt container from the Releases page rather than rebuilding.
