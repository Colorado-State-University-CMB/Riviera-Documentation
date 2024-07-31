# Riviera Quick Start

## Riviera Quick-Start

1. From a _login node_ load the slurmtools module to access the SLURM job scheduler instance for Riviera:
   ```bash
   $ module load slurmtools
   ```
*It is useful to add this command to ~/.bashrc so that slurm is loaded automatically at shell startup*

2. Once the Riviera Slurm job scheduler has been loaded you can submit and start jobs on the Riviera cluster. Consult the requesting resources section and the examples section below to learn how to direct your jobs to the appropriate Riviera compute nodes.

3. Software can be loaded into the Riviera compute environment via the LMOD [module system](../../compute/modules.md), which allows users choose software from our pre-installed software stack.

4. If you would like to use software that is not within our preinstalled stack your application must be compiled using locally. Consult our [compiling and linking documentation](https://github.com/Colorado-State-University-CMB/Code-club/blob/compute/compiling.md) for more information on compiling software.
## Cluster Summary
### Nodes
The Riviera cluster is made up of three different types of nodes outlined below:

- **CPU nodes**: 
8 nodes

| Name          | Time       |
| ------------- | ---------- |
| short-cpu     | 02:00:00   |
| day-long-cpu  | 24:00:00   |
| week-long-cpu | 7:00:00:00 |

- **GPU nodes**:
3 gnodes

| Name          | Time       |
| ------------- | ---------- |
| short-gpu     | 02:00:00   |
| day-long-gpu  | 24:00:00   |
| week-long-gpu | 7:00:00:00 |

- **High-memory nodes**:
2 mnodes

| Name              | Time       |
| ----------------- | ---------- |
| short-highmem     | 02:00:00   |
| day-long-highmem  | 24:00:00   |
| week-long-highmem | 7:00:00:00 |

## Node Features
The Riviera cluster features some heterogeneity. A variety of feature tags are applied to nodes deployed in Riviera to allow jobs to target specific CPU, GPU, network, and storage requirements.

Use the `sinfo` command to determine the features that are available on any node in the cluster.

> _**Note:**_ **Feature descriptions and finalized partitions names are still being added to Riviera nodes. Refer to the description of features list below for current node features.**

```bash
sinfo --format="%N | %f"
```

## Job Scheduling

All jobs on Riviera are run through a queue system using the SLURM job scheduler. Though many HPC workflows are run through batch-type jobs, interactive jobs on compute nodes are allowed but these must also be initiated through the scheduler.

More details about how to use SLURM to run jobs can be found in our [running applications with jobs](../../running-jobs/running-apps-with-jobs.md) documentation.