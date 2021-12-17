# Cal-Val-Example

This repository is meant to demonstrate how to organize validation data and activities on AWS and github.

# Organization

1. Creation of Cal/Val Datasets in the schematic
   + geojson with relevant metadata and urls to measurement/images
   + storing data on s3
2. Processing of datasets and validation activities

The generation of the Confusion matrix is meant to represent the final validation of requirements.


# Installation

Anaconda python and then install [mamba](https://github.com/mamba-org/mamba). Set up the environment.

```
mamba env create -f environment.yml
```

Then, `conda activate calval_env` and install the kernel for jupyter with `python -m ipykernel install --user --name
calval_env`.

# Basic Mock Up

We are going to do a very basic water/no-water analysis over 3 deltas along the Gulf-coast comparing them to similar maps made from LANDSAT (thanks Matt Hansen!)

1. [Wax Lake](https://en.wikipedia.org/wiki/Wax_Lake)
2. [Atchafalaya](https://en.wikipedia.org/wiki/Atchafalaya_Basin)
3. [Mobile-Tensaw](https://en.wikipedia.org/wiki/Mobile%E2%80%93Tensaw_River_Delta)


Below, the diagram is roughly the schematic of what we will be demonstrating in this repo.

![schematic](schematic.png)

Technically, the product data should be available from the OPERA Product API. However, this is an exercise to provide the team a clear example of how to interact with the data.

## Steps

1. Create `datasets/aois` with `QGIS` and its vector drawing tools.
2. Create an s3 bucket called `calval-metadata` in s3. Do not need to change any settings.
3. Generate AWS credentials (credentials last for 24 hours) with these [instructions](https://github.jpl.nasa.gov/cloud/Access-Key-Generation/blob/master/python-README.md); this will require JPL VPN to access the repository and to generate the proper credentials. You will clone and presumably have most of the libraries (may have to install). I just ran `python aws-python.py` without changing the file permissions and that was fine. If you are apart of more than one AWS account, you will be prompted to select the proper role.
4. Organize the landsat mosaics as [here](datasets/0_Organize_Hansen_Landsat_Mosaics.ipynb).