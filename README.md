# BarBIQ Pipeline (v1.1.0)

The BarBIQ pipeline is for processing the sequencing data (please note that this code only accept the phred+33 encoding system for the sequencing quality scores) obtained by BarBIQ method to identify Bar sequences (16S rRNA sequences) and cOTUs (cell-based taxa) and to quantify the identified cell numbers of each cOTU. 

This is version 1.1.0\
Author: Jianshi Jin\
Supervisor: Katsuyuki Shiroguchi<br/>


## What's new in this version compared to version 1.0.0

(1) For easy-to-use, all the processes are automated by two lines of commands.<br/> 
(2) Mapping to the database RDP, GreenGene, or Silva is removed.<br/>
(3) Installation is much easier.<br/>

## Contents
BarBIQ_code: All codes of this pipeline<br/>
Demo: Example data which can be used for demonstration and requires 6.5 hours of running time<br/>
Expected_output_files: Expected output after this pipeline runs correctly<br/>

## Codes
The codes of this pipeline is written in Perl (v5.22.1) or in R (version 3.6.3)(only one code). <br/>

## System requirements
Required operation system: Linux 64<br/>

## Download

Clone/download this repository to your local computer<br/>
Click "Download ZIP" button<br/>
Or<br/>
Type in the Terminal or equivalent:<br/> 
```
$ git clone https://github.com/Shiroguchi-Lab/BarBIQ_Pipeline_V1_1_0.git
```

## Installation other software
(1) Install Perl(tested v5.22.1; https://www.perl.org) if need.<br/>
(2) Install R(tested versions 3.5.1, 4.0.2, and 4.1.1; https://www.r-project.org) if need.<br/>
(3) Install nucleotide-sequence-clusterizer (Version 0.0.7) which is available at http://kirill-kryukov.com/study/tools/nucleotide-sequence-clusterizer/ <br/>
(4) Install RDPTools which is available at https://github.com/rdpstaff/RDPTools <br/>

## Install required perl modules
Type in the Terminal or equivalent with adjustment of the path, "path-to", accordingly:
```
$ cd path-to/BarBIQ_code
$ chmod a+x *
$ ./BarBIQ_check_and_install_modules.pl
```

## How to use
### Step 1: For each sequencing run
Modify the files in the "Demo" folder, BarBIQ_example_inputfile_1.txt and BarBIQ_example_parameter_1.txt, for your own data (make sure to adjust the paths, "path-to", accordingly, even for the demonstration)<br/>
Type the following command with adjustment of the path, "path-to", accordingly:<br/>
  ```
$ path-to/BarBIQ_code_1_1_0/BarBIQ_Step_1.pl --in path-to/Demo/BarBIQ_example_inputfile_1.txt --p path-to/Demo/BarBIQ_example_parameter_1.txt
  ```

### Step 2: For all samples
Modify the files in the "Demo" folder, BarBIQ_example_inputfile_2.txt and BarBIQ_example_parameter_2.txt, for your own data (make sure to adjust the paths, "path-to", accordingly, even for the demonstration)<br/>
Type the following command in the Terminal or equivalent with adjustment of the path, "path-to", accordingly:<br/>
  ```
$ path-to/BarBIQ_code_1_1_0/BarBIQ_Step_2.pl --in path-to/Demo/BarBIQ_example_inputfile_2.txt --p path-to/Demo/BarBIQ_example_parameter_2.txt
  ```


## Key output results
### "BarBIQ_Quantification.xlsx" 
In the output folder of the Step 2 contains the raw counted cell numbers, absolute cell numbers per unit weight or volume, and proportional cell abundance of the cOTUs for each sample with the taxonomies predicted by RDP classifier. <br/>

### "BarBIQ_Bar_sequences.xlsx" 
In the output folder of the Step 2 contains the Bar sequences for all samples with the cOTU information. <br/>

* For the detailed information, please refer to the "ReadMe" sheet in each file. <br/>


## Documentation
All the algorithms of this pipeline is described in the paper [High-throughput identification and quantification of single bacterial cells in the microbiota](https://www.nature.com/articles/s41467-022-28426-1).<br/>

## How to cite the BarBIQ pipeline
### Please cite the following two papers:
Jin, J., Yamamoto, R., Takeuchi, T., Cui, G., Miyauchi,E., Hojo, N., Ikuta, K, Ohno, H. & Shiroguchi, K. High-throughput identification and quantification of single bacterial cells in the microbiota. Nat. commun., 13, 863, (2022). <br/>

Ogawa, T., Kryukov, K., Imanishi, T. & Shiroguchi, K. The efficacy and further functional advantages of random-base molecular barcodes for absolute and digital quantification of nucleic acid molecules. Sci. Rep. 7, 13576 (2017).<br/>

### If you use the taxonomies for the cOTUs generated by this pipeline, please cite this paper as well:
Wang, Q, Garrity, G. M., Tiedje, J. M. & Cole, J. R. Naïve Bayesian Classifier for Rapid Assignment of rRNA Sequences into the New Bacterial Taxonomy. Appl. Environ. Microbiol. 73(16), 5261-5267 (2007).<br/>
