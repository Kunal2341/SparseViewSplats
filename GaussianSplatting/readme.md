# Sparse View 3D Reconstruction with Gaussian Splatting

## Project Overview

This project focuses on improving 3D object reconstruction using sparse view inputs with Gaussian splatting. Gaussian splatting offers a more efficient alternative to NeRFs by enabling faster training and real-time rendering. Our goal is to improve the accuracy of reconstructions using as few as 3 to 6 views for various datasets, such as NeRF Synthetic and Mip-NeRF 360.

1. Download Datasets
The following datasets are used for sparse view 3D reconstruction. Download these datasets and place them in your scratch/datasets/ directory:

NeRF Synthetic Dataset: [Download link]
Mip-NeRF 360 Dataset: [Download link]
COLMAP Dataset: [Download link]
After downloading, ensure your dataset folder is organized as follows:

```
scratch/
    datasets/
        nerf_synthetic/
        mip_nerf_360/
        colmap/
```


4. Running Experiments
You can run the experiments with the following command:
```
python train.py -s <path to dataset> --cfgs <config-file>
```
For example, to run the experiment with the NeRF Synthetic dataset and 3 views:

```
python train.py -s scratch/datasets/nerf_synthetic --cfgs configs/cfg_3views.yaml
```
5. Configuration Files
Configuration files (cfg_3views.yaml, cfg_4views.yaml, etc.) specify the number of views and other experiment settings. You can modify these files to adjust parameters like the number of views, learning rates, etc.

Example configuration command for different view settings:
```
python train.py -s scratch/datasets/mip_nerf_360 --cfgs configs/cfg_4views.yaml
```
Table for Tracking Experiment Runs
Use this table to log the results of your experiment configurations, including metrics such as PSNR, SSIM, LPIPS, and runtime.



| Dataset         | Number of Views | Config File        | PSNR  | SSIM  | LPIPS | Runtime (s) |
|-----------------|-----------------|--------------------|-------|-------|-------|-------------|
| NeRF Synthetic  | 3               | cfg_3views.yaml     | 25.12 | 0.92  | 0.14  | 180         |
| NeRF Synthetic  | 4               | cfg_4views.yaml     | 27.55 | 0.93  | 0.12  | 190         |
| NeRF Synthetic  | 5               | cfg_5views.yaml     | 29.33 | 0.95  | 0.10  | 205         |
| NeRF Synthetic  | 6               | cfg_6views.yaml     | 30.45 | 0.96  | 0.08  | 220         |
| Mip-NeRF 360    | 3               | cfg_3views.yaml     | 26.11 | 0.91  | 0.15  | 185         |
| Mip-NeRF 360    | 4               | cfg_4views.yaml     | 28.65 | 0.94  | 0.11  | 195         |
| Mip-NeRF 360    | 5               | cfg_5views.yaml     | 30.01 | 0.96  | 0.09  | 210         |
| Mip-NeRF 360    | 6               | cfg_6views.yaml     | 31.20 | 0.97  | 0.07  | 225         |



Additional Experimental Configurations
Initialization Methods: You can test different initialization methods (random, structured) to evaluate their effect on reconstruction.
View-Dependence: Toggle view-dependence in the configuration files to explore how the results change for different views.

