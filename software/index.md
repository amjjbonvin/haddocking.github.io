---
layout: page
tags: [Jekyll, HADDOCK, Bonvin, Docking, Simulation, Molecular Dynamics, Structural Biology, Computational Biology, Modelling, Protein Structure]
modified: 2014-08-08T20:53:07.573882-04:00
comments: false
image:
  feature: pages/banner_software.jpg
---

This page provide you links to software and software manuals of the computational structural biology group.

* table of contents
{:toc}


<HR>
### HADDOCK
  Software package for integrative modelling of biomolecular complexes
  
  * [**HADDOCK best practice guide**](/software/bpg) - A must read when starting to use our software!
  
  * [**HADDOCK2.4/5 software**](/software/haddock2.4/) - Official 2.4/5 production version

  * [**HADDOCK2.4 web server**](https://wenmr.science.uu.nl/haddock2.4/) - production version
  
  * [**HADDOCK3 software**](/software/haddock3) - A new, very experimental [BioExcel](https://www.bioexcel.eu) redesign of HADDOCK in a modular code. Use it at your own risk!

<HR>
### [HADDOCKING GitHub repository](https://github.com/haddocking)
  The GitHub repository for HADDOCK and its associated tools

  * [**Arctic-3D**](https://github.com/haddocking/arctic3d):
  ARCTIC-3D is a software for data-mining and clustering of protein interface information. It allows you to retrieve all the existing interface information for your desired protein from the [PDBE graph database](https://www.ebi.ac.uk/pdbe/pdbe-kb/), grouping similar interfaces in interacting surfaces.

  * [**Binding_affinity: PRODIGY**](https://github.com/haddocking/binding_affinity):
  A collection of Python scripts to predict the binding affinity in protein-protein complexes.

  * [**DisVis**](https://github.com/haddocking/disvis):
  A Python package and command-line tool to quantify and visualize the accessible interaction space of distance-restrained biomolecular complexes.

  * [**Fraction of common contact clustering**](https://github.com/haddocking/fcc):
  Clustering of biomolecular complexes based on the fraction of common contacts

  * [**HADDOCK-tools**](https://github.com/haddocking/haddock-tools):
  A collection of useful scripts related to HADDOCK

  * [**PDB-tools**](https://github.com/haddocking/pdb-tools):
  A collection of Python scripts for the manipulation (renumbering, changing chain and segIDs...) of PDB files.
  For documentation refer to [https://www.bonvinlab.org/pdb-tools/](https://www.bonvinlab.org/pdb-tools/).
  And now also available as [web portal](https://wenmr.science.uu.nl/pdbtools)!

  * [**PowerFit**](https://github.com/haddocking/powerfit):
  PowerFit is a Python package and simple command-line program to automatically fit high-resolution atomic structures in cryo-EM densities.

  * [**Samplex**](https://github.com/haddocking/samplex):
  Samplex is an automatic and unbiased method to distinguish perturbed and unperturbed regions in a protein existing in two distinct states (folded/partially unfolded, bound/unbound). Samplex takes as input a set of data and the corresponding three-dimensional structure and returns the confidence for each residue to be in a perturbed or unperturbed state.

<HR>
### 3D-DART DNA modelling
  3D-DART provides a convenient means of generating custom structural models of DNA. Our server is no longer in operation because of security issues, but you can run it yourself from a docker container. Visit for this our GitHub repo below.

  * [**3D-DART**](https://github.com/haddocking/3D-DART-server/)

<HR>
### Bioinformatics interface predictors

  * [**WHISCY**](https://nmr.chem.uu.nl/Software/whiscy/index.html)
  WHISCY is a program to predict protein-protein interfaces. It is primarily based on conservation, but it also takes into account structural information.

  * [**CPORT**](https://alcazar.science.uu.nl/services/CPORT)
  CPORT is an algorithm for the prediction of protein-protein interface residues. It combines six interface prediction methods into a consensus predictor

<HR>
### Deep learning protein interactions

  * [**DeepRank**](https://github.com/DeepRank/deeprank)
  DeepRank is a general, configurable deep learning framework for data mining protein-protein interactions (PPIs) using 3D convolutional neural networks (CNNs).
  
  * [**DeepRank-GNN**](https://github.com/DeepRank/Deeprank-GNN)
  DeepRank-GNN is a general, configurable deep learning framework for data mining protein-protein interactions (PPIs) using graph convolutional neural networks (CNNs).
  
  * [**DeepRank-GNN-esm**](https://github.com/haddocking/DeepRank-GNN-esm)
  DeepRank-GNN-esm is a general, configurable deep learning framework for data mining protein-protein interactions (PPIs) using graph convolutional neural networks (CNNs) and including language model features.

<HR>
### Benchmarks and datasets

* Docking benchmark of membrane protein complexes ([GitHub](https://github.com/haddocking/MemCplxDB)) and associated decoy dataset [ https://doi.org/10.15785/SBGRID/618]( https://doi.org/10.15785/SBGRID/618)

* Cleaned Docking Benchmark 5 dataset, HADDOCK-ready, with unbound and bound structures matched: [https://github.com/haddocking/BM5-clean](https://github.com/haddocking/BM5-clean)

* HADDOCK docking decoys for the new entries (55) of the protein-protein Docking Benchmark5: [https://data.sbgrid.org/dataset/131/](https://data.sbgrid.org/dataset/131/)

* Docking models for Docking Benchmark 4, 5 and CAPRI score_set: [https://doi.org/10.15785/SBGRID/684](https://doi.org/10.15785/SBGRID/684)

* HADDOCK refined models for the biological/crystallographic interfaces collected in the DC and MANY datasets: [https://doi.org/10.15785/SBGRID/566](https://doi.org/10.15785/SBGRID/566)

* HADDOCK models of mutant protein complexes: [https://doi.org/10.15785/SBGRID/651](https://doi.org/10.15785/SBGRID/651)

* [Protein-DNA docking benchmark](https://github.com/haddocking/Prot-DNABenchmark)

* [Protein-cyclic peptide docking benchmark](https://github.com/haddocking/cyclic-peptides) and associated models dataset [https://data.sbgrid.org/dataset/912](https://data.sbgrid.org/dataset/912)

* All-atom and Coarse-grained HADDOCK docking models for Protein-DNA complexes: [https://zenodo.org/record/3941636](https://zenodo.org/record/3941636)

* [Dataset of modelled protein-cyclic peptide complexes](https://data.sbgrid.org/dataset/912/) obtained with HADDOCK corresponding to the optimal protocol described in  [Charitou et al. JCTC 2022](https://doi.org/10.1021/acs.jctc.2c00075)
