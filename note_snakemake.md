# Snakemake

## Description
The Snakemake workflow management system is a tool to create reproducible and scalable data analyses. Workflows are described via a human readable, Python based language. They can be seamlessly scaled to server, cluster, grid and cloud environments, without the need to modify the workflow definition. Finally, Snakemake workflows can entail a description of required software, which will be automatically deployed to any execution environment.

## Document
Author provides website including tutorial. This is good source to know Snakemake well.  
[snakemake website](https://snakemake.readthedocs.io/en/stable/)

## vim syntax highlight
A vim sytax highligth definition for Snakemake is provided by following repository.  
[github: snakemake/misc/vim](https://github.com/snakemake/snakemake/tree/master/misc/vim)

To activate syntax automatically, add the following descriptions to `.vimrc`.  
```
au BufNewFile,BufRead Snakefile set syntax=snakemake
au BufNewFile,BufRead *.smk set syntax=snakemake
au BufNewFile,BufRead *.rules set syntax=snakemake
au BufNewFile,BufRead *.snakefile set syntax=snakemake
au BufNewFile,BufRead *.snake set syntax=snakemake
```
