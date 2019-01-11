# Image_Caption_Generation
## Introduction
A reimplementation of Show and Tell: Lessons Learned from the 2015 MSCOCO Image Captioning Challenge
Paper link: https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7505636
## The Network Structure
![image](https://github.com/HqWei/Image_Caption_Generation/blob/master/show_and_tell_network_structure.png)
## Result
![image](https://github.com/HqWei/Image_Caption_Generation/blob/master/Image_caption_generation/result/result1.png)

      0) a group of young men standing next to each other . (p=0.002236)
      1) a group of people standing next to each other . (p=0.001442)
      2) a group of young men standing next to each other on a field . (p=0.000307)
![image](https://github.com/HqWei/Image_Caption_Generation/blob/master/Image_caption_generation/result/result2.png)

      0) a woman standing next to a red fire hydrant . (p=0.000278)
      1) a woman sitting on a bench with a cell phone . (p=0.000023)
      2) a woman standing next to a red fire hydrant (p=0.000021)
 ## Dataset：MSCOCO、Flickr30k、Flickr8k
MSCOCO:http://cocodataset.org/

Download mscoco dataset (3 files to /Show_And_Tell/data/mscoco/raw-data path)：

Training set:
http://msvocds.blob.core.windows.net/coco2014/train2014.zip
Evaluation set: 
http://msvocds.blob.core.windows.net/coco2014/val2014.zip
Caption set:
Http://msvocds.blob.core.windows.net/annotations-1-0-3/captions_train-val2014.zip
## Download the pretrain model of InceptionV3
http://download.tensorflow.org/models/inception_v3_2016_08_28.tar.gz 
## Train 
Natural Language Toolkit (NLTK) in needed first!  Run the following code to install ：

            import nltk
            nltk.download()

Step 1: Fix the CNN parameters and train the LSTM language model 500K
CNN parameters: pre-trained good parameters in the ImageNet dataset
Training split: one sentence n words -> n-1 group training sequence

Step 2: Fine-tuning CNN parameters, CNN & LSTM training 100K together
