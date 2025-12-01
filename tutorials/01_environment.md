---
layout: default
title: Installation
nav_order: 1
parent: Tutorials
permalink: /installation
---

# Environment Setup (TSCC)

Before building FLASH, load the correct modules:

```bash
module purge
module load shared cpu/0.17.3 gcc/10.2.0-2ml3m2l
module load intel-mpi/2019.10.317-wqrwez3
module load hdf5/1.10.7-rphji2e
module load hypre/2.23.0-vldmtv6
