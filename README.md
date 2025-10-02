# Evaluating_Sentinel-2_Super-Resolution_Algorithms_for_Automated_Building_Delineation

This repository contains all references to code repositories and datasets used for my master thesis "Evaluating Sentinel-2 Super-Resolution Algorithms for Automated Building Delineation" at Technical University of Vienna.

All dataset involved in this repository are published here: *to be inserted research_data_TU*

The following repositories are included:

- austriadownloader: https://github.com/Zerhigh/austriadownloader
- austriadownloader_sampler: https://github.com/Zerhigh/austriadownloader_sampler
- cubexpress_austria: https://github.com/Zerhigh/cubexpress_austria
- dataset_preparation: https://github.com/Zerhigh/dataset_preparation
- ESAOpenSR Segmentation-Models-Benchmark: https://github.com/ESAOpenSR/Segmentation-Models-Benchmark/tree/cleanup
- master_inference_superIX: https://github.com/Zerhigh/master_inference_superIX
- master_inference_sen2sr: https://github.com/Zerhigh/master_s2_inference_sen2sr
- tracasa_data_preparation: https://github.com/Zerhigh/tracasa_data_preparation

This repository is NOT designed to be a fully reproducible environment. Most results achieved with the presented repositories are published as independent data sources in the data repository (e.g. stratified datasets, super-resolved images, and building delineation metrics & results). Thus, this repository is aimed as a reference to the created code segments which were used to create these datasets. Refer to the individual repositories for detailed descriptions.

Several different code environments were used to process the experiments (refer to each repository for specific details). Furthermore, GPU hardware was used to train building delineation models and infer SR images. This requires GPU memory >= 18GB and CUDA version >= 11. Conda and venv environments were used, depending on specific requirements.   

## Repository Descriptions

The presented overview is extended with the following in-depth description of the developed repositories and how they were used during the thesis:

### austriadownloader

The austridownloader package was developed to download and process Austrian orthophotos and cadastral masks featuring building footprints. These were used to construct the datasets for this thesis, which include temporally and spatially aligned HR orthophotos and HR cadastral masks at 2.5m spatial resolution. Additionally, extensive metadata of the downloaded images is provided. The developed package allows further refinements of datasets, which were not relevant for this thesis.   

### austriadownloader_sampler

The austriadownloader_sampler repository is used to create a uniform sampling grid across Austria, which is required as input for the austriadownlaoder package. This grid was constructed to reduce overlap between images and cover all the diverse landscapes of Austria.

### cubexpress_austria

The cubexpress_austria repository was forked from the CubeXpress package from Julio, which allows the download of Sentinel-2 images from GEE. This repository extends the original one by implementing additional methods for selecting and filtering Sentinel-2 images regarding their spectral correlation with the downloaded orthophoto dataset.

### dataset_preparation

The dataset_preparation repository deals with dataset stratifaction for generating an evenly distributed dataset. A focus is put on removing images with NoData values and classifying images based on the amount of building present. This information is used to implement a uniform distribution of rural and urban images across the training, validation, and test datasets.   

### master_inference_superIX

The master_inference_superIX repository relies on the superIX framework which allows the super-resolution of images with different available models. The functionality of the framework was extended by retaining geospatial information and interpolating super-resolved images to the uniform resolution of 2.5m, if the respective output resolution was different.

### master_inference_sen2sr

The master_inference_sen2sr repository extend the master_inference_superIX repository by focussing entirely on the SEN2SR model, which had to be used on designated hardware with CUDA>=12.0.

### tracasa_data_preparation

The tracasa_data_preparation repository deals with data processing steps necessary to perform inference with the Tracasa model, and subsequently allow the comparison of super-resolved images on the smaller Tracasa image subset.  

### Segmentation-Models-Benchmark

The 'cleanup' branch in Segmentation-Models-Benchmark encompasses all DL aspects developed for the building delineation from super-resolved Sentinel-2 images. This includes the training of networks, data handling strategies, evaluation metrics, and testing scripts. The repository is part of the ESAOpenSR project.

## Licenses

Several licenses apply to content featured in this repository:
- all individual code repositories are published under varying licenses, refer to each repository itself
- this repository is published under the MIT license
- orthophoto images and cadastral masks are published udner CC-BY-4.0
- Sentinel-2 and their derived images underly their open license published here: https://dataspace.copernicus.eu/terms-and-conditions

created 10.09.2025