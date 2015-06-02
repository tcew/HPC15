# HPC15
Tutorial for the K2I 2015 summer institute on accelerators

Running on davinci

<b> On davinci login node </b>:
 
1. Grab a copy of OCCA:

<i> git clone https://github.com/tcew/OCCA2 </i>

2. Tell OCCA where it lives by editing ~/.bashrc

<i>export OCCA_DIR=/home/username/OCCA2</i>
<br><i>export PATH=$PATH:$OCCA_DIR/bin</i>
<br><i>export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OCCA_DIR/lib</i>

3. Grab a copy of the examples:

<i>git clone https://github.com/tcew/HPC15.git</i>

4. Request a GPU node on davinci:

<i>qsub -I -l nodes=1:ppn=12:gpu,walltime=00:30:00 -W group_list=k2i -q classroom</i>

<b>On GPU node:</b>

5. Build OCCA (on the GPU node): 

<i>module load cuda</it>
<br><i>module load gcc</i>
<br><i>cd OCCA</i>
<br><i>make -j</i>

6. Test OCCA (on the GPU node):

<i>occainfo</i>
 
7. Build a simple OCCA example:

<i>cd ~/HPC15/examples/occa/simple</i>
<br><i>make </i>

8. Run OCCA example:

<i>./main</i>

