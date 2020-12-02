# Contents
<!--ts-->
   * [Contents](#contents)
   * [Common](#common)
      * [Transfer Data](#transfer-data)
   * [LSF](#lsf)
      * [Basic Commands](#basic-commands)
         * [bsub](#bsub)
         * [bjobs](#bjobs)
         * [bhist](#bhist)
         * [bkill](#bkill)
         * [bhosts(-gpu)](#bhosts-gpu)
         * [lshosts](#lshosts)
         * [bqueues](#bqueues)
         * [lsloads](#lsloads)
         * [bapp](#bapp)

<!-- Added by: shota, at: Wed Dec  2 12:13:33 JST 2020 -->

<!--te-->
# Common
## Transfer Data
The scp command is used to copy files and directories from one machine to another.  
```
scp USER_NAME@FROM_HOST:PATH_TO_FILE USER_NAME@TO_HOST:PATH_TO_FILE
```

# LSF
## Basic Commands
### bsub
Submits a job.  
* **-app <APPLICATION_PROFILE_NAME>:** Submits the job to the specified application profile
* **-cwd <PATH>:** Specifies the current working directory
* **-e <ERROR_FILE>:** Appends the standard error output to a file
* **-i <INPUT_FILE>:** Getes the stadard input for the job from specified file
* **-J <JOB_NAME>:** Assigns the specified name to the job
* **-M <MEMORY_LIMIT>:** Sets the per-process memory limit (KB)
* **-n <MIN_PROC[,MAX_PROC]>:** Specifies the minimum and maximum numbers of processors required for a parallel job
* **-o <OUTPUT_FILE>:** Appends the standard output to a file
* **-q <QUEUE_NAME>:** Submits job to one of the specified queues

### bjobs
Displays information about jobs.  

### bhist
Displays historical information about jobs.  

### bkill
Sends a signal to a job.  

### bhosts(-gpu)
Displays hosts and their static and dynamic resources.  

### lshosts
Displays hosts and their static resource information.  

### bqueues
Displays information about users and user groups.  

### lsloads
Displays dynamic load indices for hosts.  

### bapp
Displays information about jobs attached to application profiles

