# BIOB480 / BIOE548: Conservation Genetics

This [GitHub repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories) is home to materials for MSU's  BIOB480 / BIOE 548: Conservation Genetics class.  

## Class Notes

Notes from lectures are available as a [web book 
here](https://elinck.org/popgen_congen_notes/). 

## Lab Activities and Final Projects

As a complement to lectures, quizzes, and problem sets---all of which 
emphasize the fundamentals of population genetics theory with examples from the conservation biology literature---we spend three class periods learning how to perform basic manipulations and analyses of genotype data in `Python`. To do so, we work from three Jupyter notebooks, found in the `scripts/` subdriectory, where we learn the fundamentals of `Python` scripting (including performing simple arithmetic and writing functions; `01_intro_python.ipnyb`), learn basic data structures and functions from the [`scikit-allel` library](https://scikit-allel.readthedocs.io/en/stable/) (`02_intro_scikit-allel.ipnyb`), and then apply our knowledge to a graded final project, where we analyze empirical variant data from a species of conservation concern (see **Potential Datasets** below) (`03_final_project.ipynb`). 


### Potential Datasets

- **Alvord Chub** (*Siphateles alvordensis*): Data [here](https://doi.org/10.5061/dryad.ct362tv), paper [here](https://doi.org/10.1007/s10592-019-01148-6).

- **Kokanee Salmon** (*Oncorhynchus nerka*): Data [here](https://doi.org/10.5061/dryad.ffbg79cvz), paper [here](https://doi.org/10.1007/s10592-021-01418-2).

- **Lake Trout** (*Salvelinus namaycush*): Data [here](https://doi.org/10.5061/dryad.2b8f1), paper [here](https://doi.org/10.1111/mec.14361). 

- **Great Grey Owl** (*Strix nebulosa*): Data [here](https://doi.org/10.5061/dryad.1rn8pk0qm), paper [here](https://doi.org/10.1007/s10592-020-01280-8).

- **Allen's Hummingbird** (*Selasphorus sasin*): Data [here](https://doi.org/10.5061/dryad.zgmsbcc84), paper [here](https://doi.org/10.1007/s10592-020-01303-4).

- **Emperor Penguins** (*Aptenodytes forsteri*): Date [here](https://doi.org/10.5061/dryad.4s7t3), paper [here](https://doi.org/10.1111/mec.14172).  

- **Dwarf Lake Iris** (*Iris lacustrus*): Data [here](https://doi.org/10.5061/dryad.xwdbrv1jh), paper [here](https://doi.org/10.3390/plants12132557).


 - **Movaje Milkweed** (*Asclepias nyctaginifolia*): Data [here](https://doi.org/10.5061/dryad.59zw3r28c), paper [here](https://doi.org/10.1111/csp2.12987).

 - **El Dorado County Mule Ears** (*Wyethia reticulata*): Data [here](https://doi.org/10.5061/dryad.n02v6wwt2), paper [here](https://doi.org/10.3120/0024-9637-67.2.65).


 - **Alligator Snapping Turtles** (*Macrochelys* spp.): Data [here](https://doi.org/10.7291/D17H67), paper [here](https://doi.org/10.1656/058.022.0sp1201).

 - **Eastern Massasauga Rattlesnake** (*Sistrurus catenatus*): Data [here](https://doi.org/10.5061/dryad.hmgqnk9mf), paper [here](https://doi.org/10.1002/eap.2793). 

 - **Western Rattlesnake** (*Crotalus oreganus*): Data [here](https://doi.org/10.5061/dryad.fbg79cns4), paper [here](https://doi.org/10.1111/1755-0998.13090). 


- **Alpine Ibex / domestic goat hybrids** (*Capra ibex* x *hircus*): Data [here](https://doi.org/10.5061/dryad.qnk98sfrp), paper [here](https://doi.org/10.1111/eva.13761).  

- **Hawaiian Monk Seal** (*Monachus schauinslandi*): Data [here](https://doi.org/10.5061/dryad.djh9w0w72), paper [here](https://doi.org/10.3354/esr01308).  

- **Harbour Porpoise** (*Phocoena phocoena*): Data [here](https://doi.org/10.5061/dryad.4qrfj6qg6), paper [here](https://doi.org/10.1111/1755-0998.13860).  

- **Pronghorn** (*Antilocapra americana*): Data [here](https://doi.org/10.5061/dryad.8931zcrmb), paper [here](https://doi.org/10.1093/jmammal/gyaa054). 

- **Other**: Using the search function on [Dryad](https://datadryad.org/stash), enter queries including the term `vcf` in combination with a subject area and taxon of interest (e.g., "conservation genetics bird vcf"). This should restrict results to datasets that include a variant call format file ending in `.vcf`, which is what we will use for analyses of genetic diversity. To further filter possible projects, make sure that the README file includes sufficient information, and that you can easily find the associated paper, either through a Google search of the title of the project, or via a link on the right-hand side of its landing page. In general, datasets with <10,000 SNPs will be easier to work with. 

### Requirements

Before beginning, make sure you have downloaded and installed the following software: 

- [The Unix Shell](https://swcarpentry.github.io/shell-novice/) (Terminal on Mac / Linux or an emulator for Windows)
- [Python 3+](https://www.python.org/downloads/)
- [Mamba](https://mamba.readthedocs.io/en/latest/)

### Instructions 

*Note: BIOB480/BIO548 students will access JupyterLab through MSU's [Tempest HPC](https://www.montana.edu/uit/rci/tempest/) Web interface. The following instructions are for installing the necessary software and packages locally.*

1) Download SNP data from the study of your choice as a gzipped VCF file and name it in the format `species.vcf.gz`. 

2) Open Terminal. Navigate to the directory you want to work in and clone this repository (e.g. `cd coursework; git clone 
https://github.com/elinck/conservation_genetics.git`). Inside the cloned repository, create a subdirectory named `data/` (e.g., `cd conservation_genetics; 
mkdir data`). Move your VCF file into this subdirectory (`mv species.vcf.gz data/.`). 

3) Enter the following commands to install the necessary Python packages, install JupyterLab, create and activate a `mamba` environment with the necessary dependencies, and open the JupyterLab file to run analyses: 

```
mamba install -c conda-forge jupyterlab scikit-allel numpy pandas matplotlib
mamba create -n congen -c conda-forge jupyterlab scikit-allel numpy pandas matplotlib
mamba activate congen
jupyter lab analysis.ipnb
```

4) Read the instructions and text in `analysis.ipynb` and run chunks of code as needed. You will see there are 11 mandatory questions interspersed throughout (plus one extra-credit prompt). Each group should record answers to these any way they see fit. (A `.docx` file with answers, pasted code, and screenshots might be a relatively simple approach.)  
