# Enhanced Asymmetric Invertible Network for Neural Video Delivery
This is the Pytorch implementation of paper: Enhanced Asymmetric Invertible Network for Neural Video Delivery.
## Requirement
- Python 3.8(Recommend to use Anaconda)
- PyTorch >= 1.5
- NVIDIA GPU + CUDA
- Python packages: pip install numpy opencv-python lmdb pyyaml tb-nightly future

or you can use our environments(eain_env.yml), it can be found in repository, then `conda env create -f eain_env.yml`
## Dataset
The dataset(VSD4K) can be founded in [CaFM-Pytorch-ICCV2021](https://github.com/Neural-video-delivery/CaFM-Pytorch-ICCV2021)

Then download and organize data like:
```
path/datasets/DIV2K
├── DIV2K_train_HR
└── DIV2K_train_LR_bicubic
    └── X2
        └─ 00001_x2.png
    └── X3
        └─ 00001_x3.png
    └── X4
        └─ 00001_x4.png
e.g.
home/lee/datasets/DIV2K
├── DIV2K_train_HR
└──DIV2K_train_LR_bicubic
    └── X2
    └── X3
    └── X4
```
you can use `datasets_generation/extract_subimages.py` to generate patches, then put them `codes/dataset/`
## Train
We will use `train.py` for our experiments. First set a config yml file in options/train/, take x4 as an example, then run as following:
```
python train.py -opt options/train/train_EAIN_x4.yml
```
## Test
We will use `test.py` for our experiments. First set a config yml file in options/test/, take x4 as an example, then run as following:
```
python test.py -opt options/test/test_EAIN_x4.yml
```
## Acknowledgement
The code is based on [IRN](https://github.com/pkuxmq/Invertible-Image-Rescaling) and [BasicSR](https://github.com/xinntao/BasicSR).
