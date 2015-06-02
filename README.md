# HPC15
Tutorial for the K2I 2015 summer institute on accelerators

Running on davinci

<b> On davinci login node </b>:
 
<ul>
<li> Grab a copy of OCCA:

<br><i> git clone https://github.com/tcew/OCCA2 </i>
</li>
<li> Tell OCCA where it lives by editing ~/.bashrc

<br><br><i>export OCCA_DIR=/home/username/OCCA2</i>
<br><i>export PATH=$PATH:$OCCA_DIR/bin</i>
<br><i>export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OCCA_DIR/lib</i><br>
</li>

<li> Grab a copy of the examples:

<br><br><i>git clone https://github.com/tcew/HPC15.git</i><br>
</li>

<li> Request a GPU node on davinci:

<br><br><i>qsub -I -l nodes=1:ppn=12:gpu,walltime=00:30:00 -W group_list=k2i -q classroom</i>
</ul>

<br><b>On GPU node:</b>

<ul>
<li> Build OCCA (on the GPU node): 

<br><br><i>module load cuda</it>
<br><i>module load gcc</i>
<br><i>cd OCCA</i>
<br><i>make -j</i><br>

</li>

<li> Test OCCA (on the GPU node):

<br><br><i>occainfo</i><br>
 
 </li>

<li>. Build a simple OCCA example:

<br><br><i>cd ~/HPC15/examples/occa/simple</i>
<br><i>make </i><br>
</li>

<li> Run OCCA example:

<br><br><i>./main</i><br>
</li>
</ul>
