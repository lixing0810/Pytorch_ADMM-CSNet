# ADMM-CSNet

***********************************************************************************************************

Codes for model in "ADMM-CSNet: A Deep Learning Approach for Image Compressive Sensing" (TPAMI 2019)
 
If you use these codes, please cite our paper:

[1] Yan Yang, Jian Sun, Huibin Li, Zongben Xu. ADMM-CSNet: A Deep Learning Approach for Image Compressive Sensing (TPAMI 2019).

http://gr.xjtu.edu.cn/web/jiansun/publications

All rights are reserved by the authors.

Yan Yang -2021/11/04. For more detail or traning data, feel free to contact: yangyan92@stu.xjtu.edu.cn


***********************************************************************************************************



## Data link: 
https://drive.google.com/drive/folders/1UhQ01pdmO11Agc5sM61Mt7KQTN9LytNt

Download data and organise as follows in the directory:
```
### For dataset         
└── data
    ├── train
    ├── test
    ├── validate
```
## Installation
This installation guide shows you how to set up the environment for running our code using conda.

First clone the ADMM-CSNET repository
```
git clone https://github.com/lixing0810/Pytorch_ADMM-CSNet.git
cd https://github.com/lixing0810/Pytorch_ADMM-CSNet
```
Then start a virtual environment with new environment variables nad
```
conda create --name ADMM_CSNET python=3.9
conda activate ADMM_CSNET 
```
Install PyTorch 
```
pip install torch torchvision
```
Install all requirements
```
pip install -r requirements.txt
```

## Usage:

1. The nonlinear layer of ADMM-CSNET in pytorch version was supported by the torchpwl package.Replace torchpwl package in your env with which we have provided in the torchpwl folder after installing. 

2. We have provided a training mri image and mask in the data directory,please replace the dataset downlowded in the google cloud.
   The full datasets contains 100 training data,50 testing data and 50 validating data.
   The mask_20 directory in data represents 20% sample and so on.

3. The net of training was implemented by end-to-end in ADMM-CSNET of pytorch version.we have provided the final model of 20%,30%,40% sample in csnet_model directory,just replace the model name in test.py.

	Test:
	```
	python test.py
	```
 
4. For retraining you should change the data_dir and mask name in train.py and saved in the logs_csnet directory.  

	Training:
	```
	python train.py
	```
 
5. Results
   Notice:
 The optimizer of pytorch ADMM-CSNET is adam as its avaliable and faster training in big data which of matlab version used by LBFGS may cause the difference in final results.
 
| Sampling Mask | PSNR |
| ------ | ------ |
| 0.2 | 31.354 |
| 0.3 | 34.365 |
| 0.4 | 37.153 |

***********************************************************************************************************
