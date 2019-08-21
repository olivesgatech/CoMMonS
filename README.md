# CoMMonS
[CoMMonS: Challenging Microscopic Material Surface Dataset](https://github.com/olivesgatech/CoMMonS)

[OLIVES Lab, Georgia Institute of Technology](https://ghassanalregib.info/)

# Abstract
Recognizing textures and materials in real-world images has played an important role in object recognition and scene understanding. Aiming at describing objects or scenes with more detailed information, we explore how to computationally characterize apparent or latent properties (e.g. surface smoothness) of materials, i.e., computational material characterization, which moves a step further beyond material recognition. For this purpose, we introduce a large, publicly available dataset named challenging microscopic material surface dataset (CoMMonS). We utilize a powerful microscope to capture high-resolution images with fine details of fabric surfaces. The CoMMonS dataset consists of 6,912 images covering 24 fabric samples in a controlled environment under varying imaging conditions such as lighting, zoom levels, geometric variations, and touching directions. This dataset can be used to assess the performance of existing deep learning-based algorithms and to develop our own method for material characterization in terms of fabric properties such as fiber length, surface smoothness, and toweling effect.

# Dataset

![CoMMonS Texture Dataset](https://github.com/olivesgatech/CoMMonS/blob/master/thumbnail_commonsdataset.png)

A carefully designed imaging system is critical for the analysis of fabric surface images. This imaging system needs to be powerful enough to capture the fine details of fabric surfaces, which reveal the textural differences that characterize the fabrics. To accomplish this task, we use a commercial imager, Dino-lite AM73915MZT for our imaging system. Some key features of this microscope include: an optical magnification power ranging from 10X to 220X; a high resolution of 2560x1920 pixels; an automatic magnification reading (AMR) function that enables automatic magnification rate recording; an extended depth of field (EDOF) that provides enhanced image quality at high magnification rates; and an enhanced dynamic range (EDR) that provides enhanced image quality for limited dynamic range conditions. You can see our dataset acquisition setup [Demo Video1](https://www.dropbox.com/s/9eddk38fakyopap/Setup_video1.mp4?dl=0) and [Demo Video2](https://www.dropbox.com/s/qc9hhikstzo7xsq/Setup_video2.mp4?dl=0) here.

To download the data, run the following commands in the terminal or alternatively, you can click [CoMMonS_FullResolution](https://www.dropbox.com/sh/102r6p8512nmv6g/AADHOkDvCzrd3BYoWUW6KkSpa/CoMMonS_FullResolution.zip?dl=0) and [CoMMonS_Sampled](https://www.dropbox.com/sh/102r6p8512nmv6g/AADpPLArkAIg9DOos4EawoCKa/CoMMonS_Sampled.zip?dl=0) to download the data directly.:
```
# download image files with full resolutions: 
wget https://www.dropbox.com/sh/102r6p8512nmv6g/AADHOkDvCzrd3BYoWUW6KkSpa/CoMMonS_FullResolution.zip?dl=0
# download a subset of the dataset with sampled image files for training and testing: 
wget https://www.dropbox.com/sh/102r6p8512nmv6g/AADpPLArkAIg9DOos4EawoCKa/CoMMonS_Sampled.zip?dl=0
# unzip the data (full resolution):
unzip CoMMonS_FullResolution.zip
# unzip the data (sampled images):
unzip CoMMonS_Sampled.zip
```

# Dataset Characteristics and Filename Formats
We created a comprehensive dataset of images captured at the fabric surfaces under varying conditions. We have 24 samples from "MS1" to "MS24" with subjective quality evaluation for three fabric properties, i.e., fiber length, smoothness and toweling effect, respectively. We acquired images for these samples under varying conditions including six translation positions, two rotation angles, two lighting conditions, two camera zoom levels, three camera function settings (Normal/EDOF/EDR), and two sample conditions regarding touching (or pressing) directions. The pressing directions are included because they will affect a human expert in evaluating the fabric properties. Combining all these conditions, we acquired a dataset of around 6912 images with the characteristics shown as below:

|Material Samples| Translation Positions | Rotation Angles | Lighting Conditions | Camera Zoom Levels |Camera Function Settings | Sample Conditions |
|---| --- | --- |--- | --- |--- | --- |
| 24 | 6 | 2 | 2 | 2 (50/200) |3 (Normal/EDOF/EDR) | 2 (towards/opposite the pile location)|
|MS1 to MS24| x:{15, 50}, y:{128, 168, 208} | "r-30", "r60" | "l4", "l5"|z:{50, 200} |{"n", "ef3u", "edr"} | {"pile", "opp"} |

The "CoMMonS_FullResolution" folder includes 6912 full resolution images (2560x1920). The "CoMMonS_Sampled" folder includes sampled images (resolution: 300x300), which are sampled from full resolution images with different positions (x, y), rotation angles (r), zoom levels (z), a touching direction ("pile"), a lightness condition ("l5"), and a camera function setting ("ed3u"). This "CoMMonS_Sampled" folder is an example of a dataset subset for training and testing (e.g. 5: 1). Our dataset focuses on material characterization for one material (fabric) in terms of one of three properties (fiber length, smoothness, and toweling effect), facilitating a fine-grained texture classification. In this particular case, the dataset is used for a standard supervised problem of material quality evaluation. It takes fabric samples with human expert ratings as training inputs, and takes fabric samples without human subject ratings as testing inputs to predict quality ratings of the testing samples. The texture patches are classified into 4 classes according to each surface property measured by human sense of touch. For example, the human expert rates surface fiber length into 4 levels, from 1 (very short) to 4 (long), and similarly for smoothness and toweling effect. In short, the "CoMMonS_Sampled" folder includes 9 subfolders, each of which inclues both sampled images and attribute class labels.

# Citation
If you use CoMMonS dataset, please cite:
```
@inproceedings{Hu2019_CoMMonS_TextureDataset,
author   = {Y. Hu and Z. Long and A. Sunderasan and M. Alfarraj and G. AlRegib},
note     = {Available at \url{https://github.com/olivesgatech/CoMMonS}},
title    = {CoMMonS: Challenging Microscopic Material Surface Dataset},
year     = {2019}}
```

# Acknowledgement
The work was partially funded by Kolon Industries through the Kolon Center for Lifestyle Innovation at Georgia Institute of Technology.

# Questions?
The dataset is provided "as is" with no guarantees. If you have any questions, regarding the dataset, you can contact me at (huyuting@gatech.edu), or even better open an issue in this repo and we'll do our best to help.
