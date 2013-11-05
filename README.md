Hands On 
========

collection of hands on exercises

IMB
---
Download the Intel MPI Benchmark from here: http://software.intel.com/en-us/articles/intel-mpi-benchmarks
```bash
  -bash-3.2$ wget http://software.intel.com/sites/default/files/article/157859/imb-3.2.4-updated.tgz
```
Extract it:
```bash
  -bash-3.2$ tar -xvf imb-3.2.4-updated.tgz
```

Edit file imb/3.2.4/src/make_ict: change compiler from from mpiicc to cc

Compile MPI1: you should get an executable named IMB-MPI1*
```bash
  -bash-3.2$ make MPI1
```

Copy executable to work directory
```bash
  cp ./IMB-MPI1 $WORKDIR
```

Ready to run!
Let's start an interactive job:
```bash
  qsub -I -A TRN001 -l nodes=1,walltime=00:30:00
```
Now we send the executable to a compute node
```bash
   aprun ./IMB-MPI1
```

Alternatively try 2 mpi processes: 
```bash
  aprun -n2 ./IMB-MPI1
```

Now it's your turn to play. Here's some simple commands you'll need to know:
```bash
  module list
  module avail
  module del
  module swap PrgEnv-pgi PrgEnv-gnu  
```

Here's your HW:

[ ]Run MPI, IO benchmarks

[ ]Try 1,2,4,8,16 mpi processes on up to 2 nodes.

* Variations include same numa node, defferent, odd numbered

* see https://www.olcf.ornl.gov/support/system-user-guides/titan-user-guide/#340

[ ]Play with some flags found here: https://www.olcf.ornl.gov/kb_articles/using-the-aprun-command/

[ ]Find out what the hardware looks like

If you have any questions, see our guide here https://www.olcf.ornl.gov/support/system-user-guides/titan-user-guide/



