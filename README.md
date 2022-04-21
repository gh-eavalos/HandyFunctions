# HandyFunctions
Set of useful functions to smoothen the terminal experience.

## Bash
### [BasicJob](https://github.com/gh-eavalos/HandyFunctions/blob/main/Bash/BasicJob)
Job header composer, capable of parallel instructions. The command 

`Logs=/ghds/tissue/rna_datasets/DownloadedDatasets/Logs && cd $Logs && BasicJob -N Download_SRA -f $Logs/Download_SRA.sh -o $Logs/Download_SRA.out -s 10 -v 10 -p 1 -t 11-1237 -c 100`

will produce this example output (`$Logs/Download_SRA.sh`) to further populate:
```
#!/bin/sh
#$ -N  Download_SRA
#$ -j  y
#$ -V  
#$ -wd /ghds/tissue/rna_datasets/DownloadedDatasets/Logs
#$ -q  tissue.q
#$ -l  mem_free=10G,h_vmem=10G
#$ -o  /ghds/tissue/rna_datasets/DownloadedDatasets/Logs/Download_SRA.out
#$ -S  /usr/bin/sh
#$ -M  eavalos@guardanthealth.com
#$ -m  beas
#$ -pe parallel 1
#$ -t  11-1237
#$ -tc 100
```
### [eFile](https://github.com/gh-eavalos/HandyFunctions/blob/main/Bash/eFile)
Function whose utility is to string together a series of commands to generate, edit, save and make exe a file: "edit File".
The example command: `eFile /Path/To/File.extension` follows these steps:

1. Touch `file`
2. Remove `file`
3. Generate and Edit `file` (w/nano instead of vim)
4. Chmod 755 `file`

### [EnumCols](https://github.com/gh-eavalos/HandyFunctions/blob/main/Bash//EnumCols)
Utility that enumerates the columns of a `tab` separated file. The position input is the <File> to process and [optional] row to use (default to the 1st).

### [EnumColsComma](https://github.com/gh-eavalos/HandyFunctions/blob/main/Bash//EnumColsComma)
Similar to `EnumCols` taking as input a `comma` separated file.
