---
title: Batch Jobs
parent: Tutorials
nav_order: 4
---

# Submitting FLASH Batch Jobs on TSCC

Create `run_flash.sh`:

```bash
#!/bin/bash
#SBATCH --job-name=flash
#SBATCH --output=flash.out
#SBATCH --nodes=1
#SBATCH --ntasks=16
#SBATCH --partition=hotel
#SBATCH --account=htl171
#SBATCH --time=04:00:00

module purge
module load shared cpu/0.17.3 gcc/10.2.0-2ml3m2l
module load intel-mpi/2019.10.317-wqrwez3
module load hdf5/1.10.7-rphji2e
module load hypre/2.23.0-vldmtv6

export FI_PROVIDER=tcp
export I_MPI_PMI_LIBRARY=/cm/shared/apps/slurm/current/lib64/libpmi2.so
export OMP_NUM_THREADS=1

srun ./flash4
```

Submit:

```bash
sbatch run_flash.sh
```

