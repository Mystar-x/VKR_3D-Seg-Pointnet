# Pytorch Implementation of PointNet and PointNet++ 

This repo is implementation for [PointNet](http://openaccess.thecvf.com/content_cvpr_2017/papers/Qi_PointNet_Deep_Learning_CVPR_2017_paper.pdf) and [PointNet++](http://papers.nips.cc/paper/7095-pointnet-deep-hierarchical-feature-learning-on-point-sets-in-a-metric-space.pdf) in pytorch.

## Update
**2019/12/16:**

(1) Fixed some errors in previous codes and added data augmentation tricks. 

(2) Added testing codes, including segmentation, and semantic segmentation with visualization. 

(3) Organized all models into `./models` files for easy using.

## Part Segmentation
### Data Preparation
Download alignment **ShapeNet** [here](https://shapenet.cs.stanford.edu/media/shapenetcore_partanno_segmentation_benchmark_v0_normal.zip)  and save in `data/shapenetcore_partanno_segmentation_benchmark_v0_normal/`.

### Run
```
## Check model in ./models 
## E.g. pointnet2_msg
python train_partseg.py --model pointnet2_part_seg_msg --normal --log_dir pointnet2_part_seg_msg
python test_partseg.py --normal --log_dir pointnet2_part_seg_msg
```
### Performance
| Model | Inctance avg IoU| Class avg IoU 
|--|--|--|
|PointNet (Official)	|83.7|80.4	
|PointNet2 (Official)|85.1	|81.9	
|PointNet (Pytorch)|	84.3	|81.1|	
|PointNet2_SSG (Pytorch)|	84.9|	81.8	
|PointNet2_MSG (Pytorch)|	**85.4**|	**82.5**	


## Semantic Segmentation
### Data Preparation
Download 3D indoor parsing dataset (**S3DIS**) [here](http://buildingparser.stanford.edu/dataset.html)  and save in `data/Stanford3dDataset_v1.2/`.
```
cd data_utils
python collect_indoor3d_data.py
```
Processed data will save in `data/stanford_indoor3d/`.
### Run
```
## Check model in ./models 
## E.g. pointnet2_ssg
python train_semseg.py --model pointnet2_sem_seg --with_rgb --test_area 5 --log_dir pointnet2_sem_seg
python test_semseg.py --with_rgb --log_dir pointnet2_sem_seg --test_area 5 --visual
```
Visualization results will save in `log/sem_seg/pointnet2_sem_seg/visual/` and you can visualize these .obj file by [MeshLab](http://www.meshlab.net/).
### Performance
|Model  | Class avg IoU |
|--|--|
| PointNet (Official) | 41.1|
| PointNet (Pytorch) | 48.9|
| PointNet2 (Official) |N/A |
| PointNet2_ssg (Pytorch) | **53.2**|

## Visualization
### Using show3d_balls.py
```
## build C++ code for visualization
cd visualizer
bash build.sh 
## run one example 
python show3d_balls.py
```
![](/Pointnet2_pytorch/visualizer/pic.png)
### Using MeshLab
![](/Pointnet2_pytorch/visualizer/pic2.png)


## Reference By
[halimacc/pointnet3](https://github.com/halimacc/pointnet3)<br>
[fxia22/pointnet.pytorch](https://github.com/fxia22/pointnet.pytorch)<br>
[charlesq34/PointNet](https://github.com/charlesq34/pointnet) <br>
[charlesq34/PointNet++](https://github.com/charlesq34/pointnet2)

## Environments
Ubuntu 16.04 <br>
Python 3.6.7 <br>
Pytorch 1.1.0
