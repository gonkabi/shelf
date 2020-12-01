# Contents
<!--ts-->
   * [Contents](#contents)
   * [Basic Commands](#basic-commands)
   * [Useful Packages](#useful-packages)
   * [Save and Restore Environment](#save-and-restore-environment)

<!-- Added by: shota, at: Tue Dec  1 18:42:15 JST 2020 -->

<!--te-->

# Basic Commands
| Description                        | Command                                   | Note               | 
| ---------------------------------- | ----------------------------------------- | ------------------ | 
| Update                             | conda update conda                        |                    | 
| Create environment                 | conda create -n ENV_NAME                  |                    | 
| Display environment list           | conda env list                            | or "conda info -e" | 
| Copy environment                   | conda create -n NEW_NAME --clone OLD_NAME |                    | 
| Delete environment                 | conda remove -n ENV_NAME --all            |                    | 
| Add package                        | conda install PACKAGE                     |                    | 
| Add package with specified version | conda install PACKAGE==x.x.x              |                    | 
| Remove package                     | conda uninstall PACKAGE                   |                    | 
| Add channel                        | conda config --append channels CHANNEL    | e.g. conda-forge   | 

# Useful Packages
| Name      | Command                        | Description                                | 
| --------- | ------------------------------ | ------------------------------------------ | 
| xsel      | conda install -c antoined xsel | Activate clipboard on tmux                 | 
| snakemake | conda install -c bioconda      | Snakemake is a workflow management system. | 

# Save and Restore Environment
Save and restore can be done by yml.  

**Save**  
```
conda env export -n ENV_NAME > env_name.yml
```

**Restore**  
```
conda env create -f=env_name.yml
```
