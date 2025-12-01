---
title: Building FLASH
parent: Tutorials
nav_order: 2
---

# Building FLASH 4.7.1 on TSCC

Clone FLASH or upload your tarball, then create your object folder:

```bash
cd FLASH4.7.1
mkdir object
cd object
```

Copy your site configuration:

```bash
cp ../sites/tscc/Makefile.h ../
```

If the Makefile is not there, see the Makefile section for mine, and copy it into the "FLASH4.7.1" folder.

Get on an interactive session before compiling FLASH.

```bash
srun -N 1 -n 4 -t 1:00:00 -p hotel -q hotel -A htl171 --pty bash
```

This will get you on a compute node with 4 cores for 1 hour. Adjust the parameters as necessary.

Now, compile FLASH.

```bash
make -j 8
```

## Common build errors
❌ Permission denied (e.g., make_bstats)

Fix:

```bash
chmod +x *
chmod +x ../tools/*
```

❌ MPI type mismatch errors

Happen when mixing OpenMPI + system gfortran.
This tutorial avoids them by using Intel MPI instead.

