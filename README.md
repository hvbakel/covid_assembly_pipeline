### covid_assembly_pipeline

This is a wrapper pipeline for the https://github.com/mjsull/COVID_pipe repo. This wrapper pushes the data to PathogenDB.

#### To run this pipeline first clone this repo and create the conda environment for it to run in.

``` cd  <this directory>```

```conda env create --file env.yml```

Test if the conda environment works:
```conda activate covid``` 

you may need to update conda before creation

```conda update conda```

Edit covid_assembly_pipeline_wrapper_example.sh script and run the pipeline using the following command

``` ./covid_assembly_pipeline_wrapper.sh <run_folder>/<sample_folder>```

The pipeline automatically determines Thermo vs Illumina libraries and runs accordingly.


The run folder name must be in the following format
```
<runID_pipeline>
```
The following folder structure should exist for <sample_folder>
 
```
<sample_folder>
└───<sample_library1>'
│   │   <read_prefix>_1.fastq.gz
│   │   <read_prefix>_2.fastq.gz
│
└───<sample_library2>
    │   <read_prefix>_1.fastq.gz
    │   <read_prefix>_2.fastq.gz
```

n.b. can be run on one to as many read files as needed, each pair of reads should have it's own folder. 

The pipeline creates all the output data in <sample_folder> and pushes the assembly info to pathogenDB.



