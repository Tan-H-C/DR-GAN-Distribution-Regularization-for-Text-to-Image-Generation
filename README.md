# DR-GAN-Distribution-Regularization-for-Text-to-Image-Generation-Draft Version


Introduction

This project page provides pytorch code that implements the following TNNLS paper:

Title: "DR-GAN-Distribution-Regularization-for-Text-to-Image-Generation"

Arxiv: https://arxiv.org/abs/2204.07945

How to use

Python

Python2.7

Pytorch0.4 (conda install pytorch=0.4.1 cuda90 torchvision=0.2.1 -c pytorch)

tensorflow (pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.12.0-cp27-none-linux_x86_64.whl)

pip install easydict pathlib

conda install requests nltk pandas scikit-image pyyaml cudatoolkit=9.0



Data:

Download metadata for birds coco and save them to data/

python google_drive.py 1O_LtUP9sch09QH3s_EBAgLEctBQ5JBSJ ./data/bird.zip

python google_drive.py 1rSnbIGNDGZeHlsUlLdahj0RJ9oo6lgH9 ./data/coco.zip

Download the birds image data. Extract them to data/birds/

cd data/birds

wget http://www.vision.caltech.edu/visipedia-data/CUB-200-2011/CUB_200_2011.tgz

tar -xvzf CUB_200_2011.tgz

Download coco dataset and extract the images to data/coco/

cd data/coco

wget http://images.cocodataset.org/zips/train2014.zip

wget http://images.cocodataset.org/zips/val2014.zip

unzip train2014.zip

unzip val2014.zip

mv train2014 images

cp val2014/* images

Pretrained Models





DAMSM for bird. Download and save it to DAMSMencoders/

python google_drive.py 1GNUKjVeyWYBJ8hEU-yrfYQpDOkxEyP3V DAMSMencoders/bird.zip

DAMSM for coco. Download and save it to DAMSMencoders/

python google_drive.py 1zIrXCE9F6yfbEJIbNP5-YrEe2pZcPSGJ DAMSMencoders/coco.zip


DR-GAN for bird. Download and save it to models

python google_drive.py 1BmDKqIyNY_7XWhXpxa2gm6TYxB2DQHS3 models/bird_DMGAN.pth

DR-GAN for coco. Download and save it to models

python google_drive.py 1tQ9CJNiLlRLBKSUKHXKYms2tbfzllyO- models/coco_DMGAN.pth




Training

go into code/ folder

bird: python main.py --cfg cfg/bird_DRGAN.yml --gpu 0

coco: python main.py --cfg cfg/coco_DRGAN.yml --gpu 0


Validation

python main.py --cfg cfg/eval_bird.yml --gpu 0

python main.py --cfg cfg/eval_coco.yml --gpu 0

License

This code is released under the MIT License (refer to the LICENSE file for details).
