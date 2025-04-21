# t-Denosing
```
t-Denosing
├── data
│   ├── nuscenes
│   │   ├── lidarseg
│   │   ├── maps
│   │   ├── samples
│   │   ├── samples_instance_mask
│   │   ├── samples_point_label
│   │   ├── sweeps
│   │   ├── v1.0-test
|   |   ├── v1.0-trainval
│   │   ├── nuscenes2d_temporal_infos_test.pkl  # generate trajectory of moving objects for denoising 
│   │   ├── nuscenes2d_temporal_infos_train.pkl # generate trajectory of moving objects for denoising 
│   │   ├── nuscenes2d_temporal_infos_val.pkl # generate trajectory of moving objects for denoising
│   │   ├── nuScenes-map-expansion-v1.2.zip  
│   │   ├── nuScenes-lidarseg-all-v1.0.tar.bz2
│   │   ├── samples_instance_mask.zip
```
a. Download nuScenes-map-expansion-v1.2.zip [HERE](https://www.nuscenes.org/download) and put it under `t-Denoising/data/nuscenes/`. Merge it to original nuScenes dataset by running unzip nuScenes-map-expansion-v1.2.zip

b. The fold `samples_instance_mask`  includes the instance masks of nuScenes images, which are predicted by the [HTC model](configs/nuimages/htc_x101_64x4d_fpn_dconv_c3-c5_coco-20e_16x1_20e_nuim.py) pretrained on nuImages dataset. The prepared data can be downloaded [HERE](https://drive.google.com/drive/folders/1VcWBwf_mjrCLTQazl7QdS6AGjnW6ALaA?usp=sharing).

c. Download nuScenes-lidarseg annotations [HERE](https://www.nuscenes.org/download) and put it under `t-Denoising/data/nuscenes/`. Create depth and semantic labels from point cloud by running:
```shell
python tools/generate_point_label.py
```
