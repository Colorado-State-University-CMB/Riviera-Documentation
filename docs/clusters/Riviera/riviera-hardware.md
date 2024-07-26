# Riviera Hardware

## Hardware Summary
- 35 Total Nodes
- 2944 CPU Cores
- 3 PB Storage
- 24 NVIDIA A100s
- 16 Tesla V100s
## Requesting Hardware Resources
Resources are requested within jobs by passing in SLURM directives, or resource flags, to either a job script (most common) or to the command line when submitting a job. Below are some common resource directives for Riviera (summarized then detailed):
* **Gres (General Resources):** Specifies the number of GPUs (*required if using a GPU node*)
* **Partition:** Specifies node type

### General Resources (gres)

**General resources allows for fine-grain hardware specifications**. On Riviera the `gres` directive is _**required**_ to use GPU accelerators on GPU nodes. At a minimum, one would specify `--gres=gpu` in their job script (or on the command line when submitting a job) to specify that they would like to use a single gpu on their specified partition. One can also request multiple GPU accelerators on nodes that have multiple accelerators. Alpine GPU resources and configurations can be viewed as follows on a login node with the `slurm/alpine` module loaded:

```bash
$ sinfo --Format NodeList:30,Partition,Gres |grep gpu |grep -v "mi100|a100"
```

__Examples of GPU configurations/requests__:

_request a single GPU accelerator:_
```
--gres=gpu
```
_request multiple (in this case 3) GPU accelerators:_
```
--gres=gpu:3
```
### Partitions
**Nodes with the same hardware configuration are grouped into partitions**. You specify a partition using `--partition` SLURM directive in your job script (or at the command line when submitting an interactive job) in order for your job to run on the appropriate type of node. 

> **Note:** GPU nodes require the additional `--gres` directive (see above section).

Partitions available on Riviera:

| Type    | Partition         | Time       | Number of Nodes | Cores/Node |
| ------- | ----------------- | ---------- | --------------- | ---------- |
| CPU     | short-cpu         | 02:00:00   | 8               | 128        |
|         | day-long-cpu      | 24:00:00   | 8               | 128        |
|         | week-long-cpu     | 7:00:00:00 | 8               | 128        |
| GPU     | short-gpu         | 02:00:00   | 3               | 256        |
|         | day-long-gpu      | 24:00:00   | 3               | 256        |
|         | week-long-gpu     | 7:00:00:00 | 3               | 256        |
| Highmem | short-highmem     | 02:00:00   | 2               | 256        |
|         | day-long-highmem  | 24:00:00   | 2               | 256        |
|         | week-long-highmem | 7:00:00:00 | 2               | 256        |

_Request one core per node for default 2 hours
```
srun --pty--time=00:10:00 /bin/bash
```
Request 4 cores for the 24 hours
```
srun --pty--partition=day-long=cpu --cpus-per-task=4 /bin/bash
```

