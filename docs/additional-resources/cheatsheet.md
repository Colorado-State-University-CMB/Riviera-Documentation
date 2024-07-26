#  Cheat Sheet

## Accessing Riviera

### Get a research computing account on rivieria
- <insert link>
### Logging in from a terminal 
ssh <username>@riviera.colostate.edu
### Windows/Mac Clients
**PuTTY** : SSH client for Windows
**WinSCP** : SCP client for Windows
**FileZilla** : FTP client for Linux, Windows, Mac
**Xming/XQuarts** : X11 server for Windows/Mac

### Accessing Interactive Nodes/Jobs
srun --pty /bin/bash

## Monitoring Tools

#### Slurmtools
module load slurm

## Data Transfers

Transferring files between Riviera and your system
scp source <username>@riviera.colostate.edu:destination
scp <username>@riviera.colostate.edu:source destination

##### Other transfer options
**Rsync** : CLI sync utility
**Sftp** : CLI interactive utility
**Rclone** : CLI cloud transfer utility

## SLURM
SLURM is an open-source cluster management and job scheduling system for Linux clusters
#### SLURM Scheduling
**sbatch <file>** : Submits a job script <file>
**sinteractive** : Submits interactive job
**squeue -u <user>** : Show job queue for <user>
**scancel <jobid>** : Deletes the job with <jobid>
**scontrol hold <jobid>** : Hold job with <jobid>
**scontrol release <jobid>** : Release job with <jobid>
**sinfo** : Cluster status
**salloc** : Request new resource allocation 
**srun** : Launch parallel job step
**sacct** : Display job accounting information 

#### SBATCH Directives
**--nodes=<count>** : Number of nodes
**--tasks-per-node=<count>** : Processes per node 
**--ntasks=<count>** : Total processes 
**--cpus-per-task=<count>** : CPU cores per process
**--nodelist=<nodes>** : Preferred Nodes
**--exclude=<nodes>** : Nodes to avoid
**--time=<min>** : Time limit; either min or dd-hh:mm:ss
**--mem=<count>** : RAM per node; e.g 10G
**--output=<file>** : Standard output; defaults to slurm-jobid.out if omitted
**--error=<file>** : Write standard error to file 
**--array=<arrayspec>** : Define job array
**--gres=gpu:<type>** : <count> : Number of GPUs
**--mail-user=<email>** : Email for job alerts 
**--mail-type=<type>** : Email alert types: BEGIN, END, FAIL, REQUEUE, ALL
**--depend=<state>:<jobid>** : Job dependency.state = after
**--job-name=<name>** : afterok, afterany, afternotok
**--constrain=<attribute>** : Job name
**--partition=<name>** : Request CPU type: e.g. day-long-cpu, week-long-highmem

#### Slurm Environmental Variables
**SLURM_JOBID** : Job ID
**SLURM_SUBMIT_DIR** : Job submission directory
**SLURM_SUBMIT_HOST** : Name of host from which job was submitted
**SLURM_JOB_NODELIST** : Names of nodes allocated to job
**SLURM_ARRAY_TASK_ID** : Task id within job array
**SLURM_JOB_CPUS_PER_NODE** : CPU cores per node allocated to job
**SLURM_NNODES** : Number of nodes allocated to job
## Software
Riviera uses a module system called LMOD to load most software into a user's environment. Most software is not accesible by default and must be loaded in. 
#### LMOD Commands 
**module avail** : Shows all available module
**module load <module>** : Loads <module> in the environment, specify version with <module>/version**
**module spider <string>** : Searches for module names matching <string>
**module keyword <string>** : Searches for modules containing <string> in name or description
**module list** : List currently loaded modules
**module unload <module>** : Removes <module> from environment
**module purge** : Removes all modules from environment
**module save <collection>** : Saves currently loaded modules to collections
**module savelist** : Returns all saved module collections
**module describe** : Get modules in a saved collection

Important notes:
- Modules should be loaded in job schipts, interactive jobs, not on the login node