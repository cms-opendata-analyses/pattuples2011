# Pattuples production from 2011 data

The exercise produces ntuples from the 2011 AOD data using the Physics Analysis Toolkit (PAT).

You need to work in a VM properly contextualized for CMS available on the CERN Open Data Portal.

In order to run the PAT_data_repo.py to generate the pattuples 
you need to create a working area and source a proper CMS environment.

## Creating the Working Area

This step is only needed the first time.

```
cmsrel CMSSW_5_3_32
cd CMSSW_5_3_32/src
```

## Sourcing the environment 

This step is needed each time you want to run the exercise.

```
cmsenv
```

## Producing the pattuples

Clone the repo:

```
git clone https://github.com/katilp/pattuples2011.git 
cd pattuples2011
```

Set the symbolic links to the Global tag in the condition database

```
ln -sf /cvmfs/cms-opendata-conddb.cern.ch/FT_53_LV5_AN1_RUNA FT_53_LV5_AN1
ln -sf /cvmfs/cms-opendata-conddb.cern.ch/FT_53_LV5_AN1_RUNA.db FT_53_LV5_AN1_RUNA.db
```

Run: 

```
cmsRun PAT_data_repo.py 
```

The number of events is set to 1000 events for testing. Set it to -1 in order to run over all events, and add the corresponding index files in PAT_data_repo.py.

Note that the first time you run the job on the CMS Open Data VM, it will read the condition data from /cvmfs area. It will take time (an example run of a 10 Mbps line took 45 mins), but it will only happen once as the files will be cached on your VM. The job will not produce any output during this time, but you can check the ongoing processes with the command 'top' and you can monitor the progress of reading the condition data to the local cache with the command 'df'.

