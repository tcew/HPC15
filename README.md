# HPC15
Tutorial for the K2I 2015 summer institute on accelerators

You can download these instructions from here: <a href = "https://github.com/tcew/HPC15/blob/master/HPC15GPUdocs.pdf"> link</a>

Running on davinci

<b> On davinci login node </b>:
 
<ul>
<li> Grab a copy of OCCA:

<br><i> git clone https://github.com/tcew/OCCA2 </i>
</li>
<br><li> Tell OCCA where it lives by editing ~/.bashrc

<br><br><i>export OCCA_DIR=/home/username/OCCA2</i>
<br><i>export PATH=$PATH:$OCCA_DIR/bin</i>
<br><i>export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OCCA_DIR/lib</i>
</li>

<br><li> Grab a copy of the examples:

<br><br><i>git clone https://github.com/tcew/HPC15.git</i>
</li>

<br><li> Request a GPU node on davinci:

<br><br><i>qsub -I -l nodes=1:ppn=12:gpu,walltime=00:30:00 -W group_list=k2i -q classroom</i>
</ul>

<br><b>On GPU node:</b>

<ul>

<li> Set up terminal session for CUDA and OpenCL (sets path and library path): 

<br><br><i>module load cuda</it><br>

</li>

<li> Build OCCA (on the GPU node): 

<br><br><i>module load cuda</it>
<br><i>cd OCCA</i>
<br><i>make -j</i>

</li>

<br><li> Test OCCA (should report all compute devices on all thread models detected):

<br><br><i>occainfo</i>
 
 </li>

<br><li>. Build a simple OCCA example:

<br><br><i>cd ~/HPC15/examples/occa/simple</i>
<br><i>make </i>
</li>

<br><li> Run OCCA example:

<br><br><i>./main</i><br>
</li>
</ul>
