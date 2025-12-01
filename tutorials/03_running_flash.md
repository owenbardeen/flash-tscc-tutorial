---
title: Running FLASH
parent: Tutorials
nav_order: 3
---

# Running FLASH on TSCC

Load modules:

```bash
module purge
module load shared cpu/0.17.3 gcc/10.2.0-2ml3m2l
module load intel-mpi/2019.10.317-wqrwez3
module load hdf5/1.10.7-rphji2e
module load hypre/2.23.0-vldmtv6

Configure Intel MPI runtime:

```bash
export FI_PROVIDER=tcp
export I_MPI_PMI_LIBRARY=/cm/shared/apps/slurm/current/lib64/libpmi2.so
export OMP_NUM_THREADS=1

Run FLASH (example 4 ranks):

```bash
srun -n 8 --overlap ./flash4
