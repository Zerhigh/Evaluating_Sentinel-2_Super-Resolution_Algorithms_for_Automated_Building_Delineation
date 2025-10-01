# Evaluating_Sentinel-2_Super-Resolution_Algorithms_for_Automated_Building_Delineation

This repository contains all references to code repositories and datasets used for my master thesis "Evaluating Sentinel-2 Super-Resolution Algorithms for Automated Building Delineation" at Technical University of Vienna.

created 10.09.2025

All dataset involved in this repository are published here: *research_data_TU*


The following repositories are included:

- austriadownloader: https://github.com/Zerhigh/austriadownloader
- austriadownloader_sampler: https://github.com/Zerhigh/austriadownloader_sampler
- cubexpress_austria: https://github.com/Zerhigh/cubexpress_austria
- dataset_preparation: https://github.com/Zerhigh/dataset_preparation
- ESAOpenSR:
- master_inference_superIX: https://github.com/Zerhigh/master_inference_superIX
- tracasa_data_preparation:

This repository is NOT designed to be a fully reproducible environment. Most results achieved with the presented repositories are published as independent data sources in the data repository (e.g. stratified datasets, super-resolved images, and building delineation metrics & results). Thus, this repository is aimed as a reference to the created code segments which were used to create these datasets. Refer to the individual repositories for detailed descriptions.

Several different code environments were used to process the experiments (refer to each repository for specific details). Furthermore, GPU hardware was used to train building delineation models and infer SR images. This requires GPU memory >= 18GB and CUDA version >= 11. Conda and venv environments were used, depending on specific requirements.   

## Repository Descriptions