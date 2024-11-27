# BIOB480 / BIOE548: Conservation Genetics

This [GitHub repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories) is home to the data and code for 
end-of-semester projects in BIOB480 / BIOE548 in the Department of Ecology at Montana State University. Students work in groups of 3-5 to analyze empirical genetic or genomic data from a population of wild plants or animals. Specifically, each group will select a published dataset and population 
genetic metric, read the associated scientific article, load the data into a Jupyter Notebook, and perform simple analyses using the Python package [scikit-allel](https://scikit-allel.readthedocs.io/en/stable/index.html). Learning outcomes include gaining familiarity with Python and scriptable anlayses of genomic data more broadly, learning how sequence data and genotypes are encoded into data objects.  All groups will present their work during final two class period. 

## Potential Datasets

- **Alvord Chub** (*Siphateles alvordensis*): Data [here](https://doi.org/10.5061/dryad.ct362tv), paper [here](https://doi.org/10.1007/s10592-019-01148-6).

- **Kokanee Salmon** (*Oncorhynchus nerka*): Data [here](https://doi.org/10.5061/dryad.ffbg79cvz), paper [here](https://doi.org/10.1007/s10592-021-01418-2).

- **Lake Trout** (*Salvelinus namaycush*): Data [here](https://doi.org/10.5061/dryad.2b8f1), paper [here](https://doi.org/10.1111/mec.14361). 

- **Great Grey Owl** (*Strix nebulosa*): Data [here](https://doi.org/10.5061/dryad.1rn8pk0qm), paper [here](https://doi.org/10.1007/s10592-020-01280-8).

- **Allen's Hummingbird** (*Selasphorus sasin*): Data [here](https://doi.org/10.5061/dryad.zgmsbcc84), paper [here](https://doi.org/10.1007/s10592-020-01303-4).

- **Emperor penguins** (*Aptenodytes forsteri*): Date [here](https://doi.org/10.5061/dryad.4s7t3), paper [here](https://doi.org/10.1111/mec.14172).  

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

## Requirements

Before beginning, make sure you have downloaded and installed the following software: 

- [The Unix Shell](https://swcarpentry.github.io/shell-novice/) (Terminal on Mac / Linux or an emulator for Windows)
- [Python 3+](https://www.python.org/downloads/)
- [Mamba](https://mamba.readthedocs.io/en/latest/)

## Instructions 

*Note: BIOB480/BIO548 students will access JupyterLab through MSU's [Tempest HPC](https://www.montana.edu/uit/rci/tempest/) Web interface. The following instructions are for installing the necessary software and packages locally.*

1) Download SNP data from the study of your choice as a gzipped VCF file and label it in the format `species.vcf.gz`. 

2) Open Terminal. Navigate to the directory you want to work in and clone this repository (e.g. `cd coursework; git clone https://github.com/elinck/conservation_genetics.git`). Inside the cloned repository, creat subdirectory labeled `data/` (e.g., `cd conservation_genetics; mkdir data`). Move your VCF file into this subdirectory (`mv species.vcf.gz data/.`). 

3) Enter the following commands to install the necessary Python packages, install JupyterLab, create and activate a `mamba` environment with the necessary dependencies, and open the JupyterLab file to run analyses: 

```
mamba install -c conda-forge jupyterlab scikit-allel numpy pandas matplotlib
mamba create -n congen -c conda-forge jupyterlab scikit-allel numpy pandas matplotlib
mamba activate congen
jupyter lab analysis.ipnb
```

4) Read the instructions and text in `analysis.ipynb` and run chunks of code as needed. You will see there are 11 mandatory questions interspersed throughout (plus one extra-credit prompt). Each group should record answers to these any way they see fit. (A `.docx` file with answers, pasted code, and screenshots might be a relatively simple approach.)  