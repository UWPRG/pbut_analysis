# “Elucidating the molecular interactions between uremic toxins and the Sudlow II binding site of human serum albumin”
Josh Smith and Jim Pfaendtner
---

In the interest of transparent and reproducible science, we offer this code repository as a supplement to the paper listed above. The repo houses the analysis code and instructions necessary to reproduce and extend our methods. All of the computational tools we describe in the following instructions are open source (freely available to YOU!). We hope this repo will serve as a useful resource for other researchers studying protein bound uremic toxins, and protein-ligand complexes in general.

### Required Software

As mentioned above, the Pfaendtner Research Group (PRG) simply _loves_ open source software. Using and creating software that is freely available is an excellent way to promote transparency and reproducibility in computational science. We used the following open source software to perform our analyses:

- Gromacs (2018.3)
- Plumed (2.4)
- python (3.6)

It will be easiest to apply our methods to a project of your own if you use these tools as well, and we would recommend these as generally useful tools for biomolecular simulations. 

If you are a seasoned MD professional - capable of calculating interaction energies and order parameters from an MD trajectory - but you don't use GROMACS and/or Plumed, you should be able to adapt our python scripts to read outputs from your engine of choice. Our clustering and energetic analyses simply require that you can coerce your data into pandas DataFrames and/or numpy arrays (see read_plumed_file() in util.py for an example). 


### Instructions

Step 1 - Follow the equilibration/simulation protocol described in our paper to create triplicate simulations of your protein-ligand complex in aqueous (?) solution.

Step 2 - Calculate atomic and hydrophilic contacts with `plumed driver`.

Step 3 - Identify key residues by filtering contact data (`coord-driver-analysis.ipynb`).

Step 4a - Calculate center of mass distance from ligand to "key residues" identified in Step 3 with `plumed driver`.

Step 4b - Use `gmx mdrun rerun` to calculate ligand-residue interaction energies.

Step 5 - Perform interaction energetic analyses in python (`interaction-energy.ipynb`).

Step 6 - Perform principal component analysis (PCA) and MeanShift clustering in python (`cluster-states.ipynb`).






