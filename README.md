# DR-GAN-Distribution-Regularization-for-Text-to-Image-Generation

Introduction
This project page is submitted to XXX:

Arxiv: xxx

How to use
Python

Python2.7
Pytorch0.4 (conda install pytorch=0.4.1 cuda90 torchvision=0.2.1 -c pytorch)
tensorflow (pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.12.0-cp27-none-linux_x86_64.whl)
pip install easydict pathlib
conda install requests nltk pandas scikit-image pyyaml cudatoolkit=9.0
Data

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
Pretrained Models Waitting

Training

go into code/ folder
bird: python main.py --cfg cfg/bird_DRGAN.yml --gpu 0
coco: python main.py --cfg cfg/coco_DRGAN.yml --gpu 0
Validation

Images generation:
go into code/ folder
python main.py --cfg cfg/eval_bird.yml --gpu 0
python main.py --cfg cfg/eval_coco.yml --gpu 0
Inception score (IS for bird, IS for coco):
cd LE-GAN/eval/IS/bird && python inception_score_bird.py --image_folder ../../../models/bird_LEGAN
cd LE-GAN/eval/IS/coco && python inception_score_coco.py ../../../models/coco_LEGAN
License
This code is released under the MIT License (refer to the LICENSE file for details).
