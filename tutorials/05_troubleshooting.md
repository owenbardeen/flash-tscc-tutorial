---
title: Troubleshooting
parent: Tutorials
nav_order: 5
---

# Troubleshooting

## ❌ FLASH hangs on srun
Likely not on a compute node.

```bash
echo $SLURM_JOB_ID
```

If empty, you are on a login node.
Start an interactive job.

## ❌ Permission denied (flash4 or make_bstats)

```bash
chmod +x flash4
chmod -R +x *
```

## ❌ MPI type mismatch errors

Cause: Using OpenMPI + system gfortran

Fix: Use Intel MPI
(See Environment Setup)

## ❌ srun: command not found

Add Slurm:

```bash
export PATH=/cm/shared/apps/slurm/current/bin:$PATH
```

## ❌ HDF5/Hypre not found

Ensure modules:

```bash
module load hdf5/1.10.7-rphji2e
module load hypre/2.23.0-vldmtv6
```







