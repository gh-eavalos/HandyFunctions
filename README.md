# HandyFunctions
Set of useful functions to smoothen the terminal experience.

## Shell
### BasicJob
Job header composer, capable of parallel instructions. Example output to further populate:
``` #!/bin/sh
#$ -cwd
#$ -N  Download_SRA
#$ -j  y
#$ -V  
#$ -q  tissue.q
#$ -l  mem_free=10G,h_vmem=10G
#$ -o  /ghds/tissue/rna_datasets/DownloadedDatasets/Logs/Download_SRA.out
#$ -S  /usr/bin/sh
#$ -M  eavalos@guardanthealth.com
#$ -pe parallel 1
#$ -t  11-1237
#$ -tc 100
```
