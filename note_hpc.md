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
      * [Job Array](#job-array)

<!-- Added by: shota, at: Wed Dec  2 16:48:39 JST 2020 -->

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
* **-cwd <SPECIFIED_PATH>:** Specifies the current working directory
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

## Job Array
Use option -J[START-END:STEP] to submit job array.  
LSF sets LSB_JOBINDEX in the execution environment to the job array index of the current job. LSB_JOBINDEX is set for all jobs. For non-array jobs, LSB_JOBINDEX is set to zero.  

Example code
```
bsub -J array[1-4] sh test_arrayjob.sh
```

Content of test_arrayjob.sh
```
#!/bin/sh
mkdir -p output/arrayjob
OUTPUT_PREFIX="./output/arrayjob/test_"/
echo "Array Number: "$LSB_JOBINDEX > $OUTPUT_PREFIX$LSB_JOBINDEX".txt"/
```

Content of ./output/arrayjob/test_1.txt.
```
Array Number: 1
```

The job array job slot limit is used to specify the maximum number of jobs submitted from a job array that are allowed to run at any one time.  
JOB_SLOT_LIMIT must be a positive integer less than the maximum index value of the job array.  
```
bsub -J JOBNAME[INDEX_LIST]%JOB_SLOT_LIMIT
```

