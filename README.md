# HPC15
Tutorial for the K2I 2015 summer institute on accelerators

Running on davinci

<b> On davinci login node </b>:
 
<ul>
<li> Grab a copy of OCCA:

<br><i> git clone https://github.com/tcew/OCCA2 </i>
</li>
<li> Tell OCCA where it lives by editing ~/.bashrc

<br><i>export OCCA_DIR=/home/username/OCCA2</i>
<br><i>export PATH=$PATH:$OCCA_DIR/bin</i>
<br><i>export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OCCA_DIR/lib</i>
</li>

<li> Grab a copy of the examples:

<br><i>git clone https://github.com/tcew/HPC15.git</i>
</li>

<li> Request a GPU node on davinci:

<br><i>qsub -I -l nodes=1:ppn=12:gpu,walltime=00:30:00 -W group_list=k2i -q classroom</i>
</ul>

<b>On GPU node:</b>

<ul>
<li> Build OCCA (on the GPU node): 

<br><i>module load cuda</it>
<br><i>module load gcc</i>
<br><i>cd OCCA</i>
<br><i>make -j</i>

</li>

<li> Test OCCA (on the GPU node):

<br><i>occainfo</i>
 
 </li>

<li>. Build a simple OCCA example:

<br><i>cd ~/HPC15/examples/occa/simple</i>
<br><i>make </i>
</li>

<li> Run OCCA example:

<br><i>./main</i>
</li>
</ul>
