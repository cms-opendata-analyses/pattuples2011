# Pattuples production from 2011 data

The exercise produces tuples created following the Physics Analysis Toolkit (pattuples) from the 2011 AOD data.

You need to work in a VM properly contextualized for CMS.

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

## Set the symbolic links to the condition database

```
ln -sf /cvmfs/cms-opendata-conddb.cern.ch/FT_53_LV5_AN1_RUNA FT_53_LV5_AN1
ln -sf /cvmfs/cms-opendata-conddb.cern.ch/FT_53_LV5_AN1_RUNA.db FT_53_LV5_AN1_RUNA.db
```

Run: 

```
cmsRun PAT_data_repo.py 
```

In this case the pattuples production was splitted in some executions per dataset (DoubleMu and DoubleElectron);
each runs over aprox. 100 files. 

