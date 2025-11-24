# Artic Batches SARS-CoV2

This set of scripts was written in order to facilitate running the Artic minion workflow on batches 

## Prerequisites

- A working installation of Mamba (see https://conda-forge.org/download/)
- A list of run accessions downloaded from the SRA Run Selector (default: `SRR_Acc_List.txt`)
- The `enaBrowserTools` package available at https://github.com/enasequence/enaBrowserTools whose `python3` directory needs to be exported to your `PATH` 

## What to expect

- A directory containing: the scripts, directory trees of: raw data, preprocessed data, results and Artic primer scheme versions for SARS-CoV2 and other major viruses
- A new mamba environment suited to run this workflow, including a directory for clair3 models that can be seen by running `ls $CONDA_PREFIX/bin/models`

## How to run

(Note: It is recommended to look inside any script here before running it)

1) Execute the code found in the script `env_setup` as needed
2) Verify the contents of your `SRR_Acc_List.txt` file and its path `~/Downloads/SRR_Acc_List.txt`.
3) Run `AccList_Download` and verify that your files were downloaded and not cancelled by FTP request denials
4) Run `Acclist_Guppyplex` which will preprocess your data
5) Check that the variables at the start of script `minion_batch` are suitable for your input data and system
6) Run `minion_batch` to perform alignment and variant calling on all of your samples 
7) Perform downstream analyses of your choice
