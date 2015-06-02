# HPC15
Tutorial for the K2I 2015 summer institute on accelerators

Running on davinci

<b> On davinci login node </b>:
 
1. Grab a copy of OCCA:

<i> git clone https://github.com/tcew/OCCA2 </i>

2. Tell OCCA where it lives by editing ~/.bashrc

<br><i>export OCCA_DIR=/home/username/OCCA2</i>
<br><i>export PATH=$PATH:$OCCA_DIR/bin</i>
<br><i>export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OCCA_DIR/lib</i>

3. Grab a copy of the examples:

<it>git clone https://github.com/tcew/HPC15.git</it>

4. Request a GPU node on davinci:

<it>qsub -I -l nodes=1:ppn=12:gpu,walltime=00:30:00 -W group_list=k2i -q classroom</it>

<b>On GPU node:</b>

5. Build OCCA (on the GPU node): 

<it>module load cuda</it>
<it>module load gcc</it>
<it>cd OCCA</it>
<it>make -j</it>

6. Test OCCA (on the GPU node):

<it>occainfo</it>
 
7. Build a simple OCCA example:

<it>cd ~/HPC15/examples/occa/simple</it>
<it>make </it>

8. Run OCCA example:

<it>./main</it>

