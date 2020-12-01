# Contents
<!--ts-->
   * [Contents](#contents)
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

<!-- Added by: shota, at: Tue Dec  1 14:57:07 JST 2020 -->

<!--te-->

# LSF
## Basic Commands
### bsub
Submits a job.  
* **-app *application_profile_name*:** Submits the job to the specified application profile
* **-cwd:** Specifies the current working directory
* **-e *error_file*:** Appends the standard error output to a file
* **-i *input_file*:** Getes the stadard input for the job from specified file
* **-J *job_name*:** Assigns the specified name to the job
* **-M *mem_limit*:** Sets the per-process memory limit (KB)
* **-n *min_proc[,max_proc]*:** Specifies the minimum and maximum numbers of processors required for a parallel job
* **-o *output_file*:** Appends the standard output to a file
* **-q *queue_name*:** Submits job to one of the specified queues

### bjobs
Displays information about jobs.  

### bhist
Displays historicalinformation about jobs.  

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

