# HPC15
Tutorial for the K2I 2015 summer institute on accelerators

Running on davinci

<b> On davinci login node </b>:
 
1. Grab a copy of OCCA:

git clone https://github.com/tcew/OCCA2

2. Tell OCCA where it lives by editing ~/.bashrc

export OCCA_DIR=/home/username/OCCA2
export PATH=$PATH:$OCCA_DIR/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OCCA_DIR/lib

3. Grab a copy of the examples:

git clone https://github.com/tcew/HPC15.git

4. Request a GPU node on davinci:

qsub -I -l nodes=1:ppn=12:gpu,walltime=00:30:00 -W group_list=k2i -q classroom

On GPU node:

5. Build OCCA (on the GPU node): 

module load cuda
module load gcc
cd OCCA
make -j

6. Test OCCA (on the GPU node):

occainfo
 
7. Build a simple OCCA example:

cd ~/HPC15/examples/occa/simple
make 

8. Run OCCA example:

./main
