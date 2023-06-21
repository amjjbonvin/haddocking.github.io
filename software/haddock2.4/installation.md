---
layout: page
tags: [Jekyll, HADDOCK, Bonvin, Docking, Simulation, Molecular Dynamics, Structural Biology, Computational Biology, Modelling, Protein Structure]
modified: 2014-08-08T20:53:07.573882-04:00
comments: false
title: HADDOCK2.4 manual - Installation Instructions
image:
  feature: pages/banner_software.jpg
---

* table of contents
{:toc}


## Installing HADDOCK


* * *

### Downloading HADDOCK

To obtain HADDOCK2.4 fill the [HADDOCK license form](https://www.bonvinlab.org/software/haddock2.4/download){:target="_blank"} ).


* * *

### Downloading CNS
The other required piece of software to run HADDOCK is its computational engine, CNS (Crystallography and NMR System – [https://cns-online.org](https://cns-online.org){:target="_blank"} ). CNS is freely available for non-profit organisations. In order to get access to all features of HADDOCK you will need to recompile CNS using the additional files provided in the HADDOCK distribution in the `cns1.3` directory. Compilation of CNS might be non-trivial. We are providing some instructions [here](https://www.bonvinlab.org/haddock3/CNS.html){:target="_blank"}. Consult also for some guidance the related entry in the [HADDOCK forum](https://ask.bioexcel.eu/t/cns-errors-before-after-recompilation/54/23){:target="_blank"}  


### Python2.7

[python](https://www.python.org){:target="_blank"} version 2.7 is required in order to run HADDOCK2.4. Importantly, python2 (pointing to python2.7) should be existing on your system.

As python2.7 is end of life, one way to install it is to use [miniconda](https://docs.conda.io/en/latest/miniconda.html){:target="_blank"} on your system.


### Biopython 1.72 (only required to use the coarse-graining option in HADDOCK2.4)

[Biopython](https://biopython.org/wiki/Download){:target="_blank"} version 1.72 is required in order to be able to convert the atomistic models into coarse grained models (see [coarse graining PDB files for docking](/software/haddock2.4/pdb-cg){:target="_blank"}. 


### DSSP (only required to use the coarse-graining option in HADDOCK2.4)

[DSSP](https://github.com/cmbi/dssp){:target="_blank"} is required to define the secondary structure, an information required to select the proper backbone parameter for the Martini coarse grained model (see [coarse graining PDB files for docking](/software/haddock2.4/pdb-cg){:target="_blank"}.


* * *

### Recommended auxiliary software


#### FreeSASA

In order to identify surface-accessible residues to define restraints for HADDOCK we can make use of [NACCESS][link-naccess]{:target="_blank"} freely available to non-profit users, or its open-source software alternative [FreeSASA][link-freesasa]{:target="_blank"}. We will here make use of FreeSASA. Following the download and installation instructions from the [FreeSASA website][link-freesasa]{:target="_blank"}. The direct download command is:

<pre style="background-color:#DAE4E7">
  wget https://github.com/mittinatten/freesasa/archive/refs/tags/2.0.3.tar.gz
</pre>

If running into problems you might want to disable `json` and `xml` support. Here we will assume you save the tar archive under the `software` directory in your home directory:

<pre style="background-color:#DAE4E7">
  tar xvfz freesasa-2.0.3.tar.gz
  cd freesasa-2.0.3
  ./configure \-\-disable-json \-\-disable-xml \-\-prefix ~/software
  make
  make install
</pre>


#### HADDOCK-tools

[HADDOCK-tools][link-haddocktools]{:target="_blank"}** is collection of HADDOCK-related scripts freely available from our GitHub repository. To install it:

<pre style="background-color:#DAE4E7">
  cd ~/software
  git clone https://github.com/haddocking/haddock-tools
</pre>

In case git is not installed on your system, go the GitHub site given in the command and download directly the archive.


#### MolProbity

[MolProbity][link-molprobity]{:target="_blank"} is a structure validation software suite developed in the Richardson lab at Duke University. In the context of HADDOCK we are making use of MolProbity to define the protonation state of Histidine residues using the `reduce` application. An pre-compiled executable can be freely downloaded from the [MolProbity GitHub website](https://github.com/rlabduke/MolProbity){:target="_blank"}. You can directly download the `reduce` executable for [Linux](https://github.com/rlabduke/MolProbity/blob/master/bin/linux/reduce){:target="_blank"} or [OSX](https://github.com/rlabduke/MolProbity/blob/master/bin/macosx/reduce){:target="_blank"}.

Put the executable for example in `~software/bin` or some other software installation directory in your path, 
rename it to `reduce` if needed and make sure it is executable (e.g. `chmod +x ~/software/bin/reduce`).


#### PDB-tools

[PDB-tools][link-pdbtools]{:target="_blank"} is a useful collection of Python scripts for the manipulation (renumbering, changing chain and segIDs...) of PDB files is freely available from our GitHub repository. To install it:

<pre style="background-color:#DAE4E7">
  cd ~/software
  git clone https://github.com/haddocking/pdb-tools
</pre>

In case git is not installed on your system, go the GitHub site given in the command and download directly the archive.


#### ProFit

[ProFit][link-profit]{:target="_blank"} is designed to be the ultimate protein least squares fitting program. Some of the provided analysis tools in HADDOCK make use of Profit. Profit can be obtained free of charge for both non-profit and commercial users. The latter should notify the authors that they are using it. For information and download see the [ProFit webpage][link-profit]{:target="_blank"}.


#### PyMol

[PyMol][link-pymol]{:target="_blank"} is a visualisation software. It is used throughout our [tutorials](/education).


* * *

### Configuring HADDOCK

After having downloaded HADDOCK, unpack the archive under the installation directory with the following command:

<pre style="background-color:#DAE4E7">
  tar xvfz haddock2.4.tgz
</pre>

In case you installed miniconda, create a HADDOCK2.4 environment with the
following command (withing the haddock2.4 directory):

<a class="prompt prompt-cmd">
conda env create -f requirements.yml
</a>

Then activate the haddock2.4 environment with:

<a class="prompt prompt-cmd">
conda activate haddock2.4
</a>


Edit then a configuration file specific to your system.

This configuration file should contain the following information:

`CNSTMP` defining the location of your CNS executable

`QUEUETMP` defining the submission command for running the jobs (e.g. either via `csh` or through a specific command submitting to your local batch system)

`NUMJOB` defining the number of concurrent jobs executed (or submitted).

`QUEUESUB` defining the HADDOCK python script used to run the jobs (the default _QueueSubmit_concat.py_ should do in most cases).


And example configuration file for running on local resources assuming a 4 core system would be:

<pre style="background-color:#DAE4E7">
  set CNSTMP=/home/software/cns/cns_solve-1.31-UU-Linux64bits.exe
  set QUEUETMP=/bin/csh
  set NUMJOB=4
  set QUEUESUB=QueueSubmit_concat.py
</pre>

For submitting to a batch system instead you might want to use a wrapper script. An example for torque can be found [here](/software/haddock2.4/faq){:target="_blank"}.

In order to configure HADDOCK, call the `install.csh` script with as argument the configuration script you just created:

<pre style="background-color:#DAE4E7">
  ./install.csh my-config-file
</pre>

There is one more file that should be manually edited to define the number of models to concatenate within one job (useful when submitting to a batch system to ensure jobs are not too short in queue).
Depending on the size of your system, a typical run time for rigid body docking would be a few tens of seconds per model written to disk (which effectively correspond to 10 docking trials internally), and a few minutes per model for the flexible refinement and water refinement. But this can increase a lot depending on the complexity of your system and the number of molecules to dock.


To define the number of concatenated models edit Haddock/Main/MHaddock.py located in the haddock2.4 installation directory and change the values as required, e.g.:

<pre style="background-color:#DAE4E7">
jobconcat["0"] = 5
jobconcat["1"] = 1
jobconcat["2"] = 1
</pre>

If running on local system, change all values to 1.

OneOne last command to source the HADDOCK environment (under bash) (for csh, replace `.sh` by `.csh`):

<pre style="background-color:#DAE4E7">
  cd ~/software/haddock2.4
  source ./haddock_configure.sh
</pre>


At this stage you should be ready to use HADDOCK2.4!

* * *


[link-cns]:CNS_manual.pdf "CNS online"
[link-data]: https://milou.science.uu.nl/cgi/services/DISVIS/disvis/disvis-tutorial.tgz "DisVis tutorial data"
[link]: https://www.pymol.org/ "PyMOL"
[link-haddock]: https://bonvinlab.org/software/haddock2.2 "HADDOCK 2.2"
[link-manual]: https://www.bonvinlab.org/software/haddock2.2/manual/ "HADDOCK Manual"
[link-forum]: https://ask.bioexcel.eu/c/haddock "HADDOCK Forum"
[link-naccess]: https://www.bioinf.manchester.ac.uk/naccess/ "NACCESS"
[link-freesasa]: https://github.com/mittinatten/freesasa/releases/tag/2.0.3 "FreeSASA"
[link-profit]: http://www.bioinf.org.uk/software/profit/ "ProFit"
[link-pymol]: https://www.pymol.org/ "PyMOL"
[link-molprobity]: https://molprobity.biochem.duke.edu "MolProbity"
[link-pdbtools]: https://github.com/haddocking/pdb-tools "PDB-Tools"
[link-haddocktools]: https://github.com/haddocking/haddock-tools "HADDOCK-Tools"
