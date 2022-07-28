# GQNet
This is the implementation of our paper [**Few-Shot Segmentation with Global and Local Contrastive Learning**](https://arxiv.org/pdf/2108.05293). 

# Get Started

### Environment
+ torch==1.4.0 (torch version >= 1.0.1.post2 should be okay to run this repo)
+ numpy==1.18.4
+ tensorboardX==1.8
+ cv2==4.2.0


### Datasets and Data Preparation

Please download the following datasets:

+ PASCAL-5i is based on the [**PASCAL VOC 2012**](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/) and [**SBD**](http://home.bharathh.info/pubs/codes/SBD/download.html) where the val images should be excluded from the list of training samples.

+ [**COCO 2014**](https://cocodataset.org/#download).

This code reads data from .txt files where each line contains the paths for image and the correcponding label respectively. Image and label paths are seperated by a space. Example is as follows:

    image_path_1 label_path_1
    image_path_2 label_path_2
    image_path_3 label_path_3
    ...
    image_path_n label_path_n

Then update the train/val/test list paths in the config files.

### Run Demo / Test with Pretrained Models
+ Please download the pretrained models.
+ We provide **8 pre-trained models**: 4 ResNet-50 based [**models**] for COCO.
+ Execute `mkdir initmodel` at the root directory.
+ Download the ImageNet pretrained [**backbones**](https://mycuhk-my.sharepoint.com/:u:/g/personal/1155122171_link_cuhk_edu_hk/EQEY0JxITwVHisdVzusEqNUBNsf1CT8MsALdahUhaHrhlw?e=4%3a2o3XTL&at=9) and put them into the `initmodel` directory.
+ Then execute the command: 

    `sh test.sh {*dataset*} {*model_config*}`

Example: Test PFENet with ResNet50 on the split 0 of PASCAL-5i: 

    sh test.sh pascal split0_resnet50


### Train

Execute this command at the root directory: 

    sh train.sh {*dataset*} {*model_config*}


# Related Repositories

This project is built upon PFENet. Many thanks to their greak work!

# Citation

If you find this project useful, please consider citing:
```
@article{liu2021few,
  title={Few-shot segmentation with global and local contrastive learning},
  author={Liu, Weide and Wu, Zhonghua and Ding, Henghui and Liu, Fayao and Lin, Jie and Lin, Guosheng},
  journal={arXiv preprint arXiv:2108.05293},
  year={2021}
}
```
