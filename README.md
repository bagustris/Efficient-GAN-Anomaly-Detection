#  Efficient-GAN-Based Anomaly Detection

Official implementation of the prepublished article submitted to the ICLRW 2018: https://arxiv.org/abs/1802.06222

NEW! Updated version of this work in ["Adversarially Learned Anomaly Detection" paper](https://arxiv.org/abs/1812.02288)!

Anomaly Detection materials, by the Deep Learning 2.0 team in I2R, A*STAR, Singapore

Please reach us via emails or via github issues for any enquiries!

Please cite our work if you find it useful for your research and work:
```
@article{zenati2018,
  author    = {Houssam Zenati and
               Chuan Sheng Foo and
               Bruno Lecouat and
               Gaurav Manek and
               Vijay Ramaseshan Chandrasekhar},
  title     = {Efficient GAN-Based Anomaly Detection},
  year      = {2018},
  url       = {http://arxiv.org/abs/1802.06222},
  archivePrefix = {arXiv}
}
```

## Prerequisites
**Please use docker as described here: https://bagustris.blogspot.com/2022/03/mencoba-docker.html**

To run the code, follow those steps:

Make virtual env via Conda/Mini conda
Link: https://docs.conda.io/en/latest/miniconda.html 

Then, create new env, e.g.,
```
conda create -n nvidia-tensorflow1.15 python=3.8
conda activate nvidia-tensorflow1.15
```
Clone or download the project code:

```
git clone https://github.com/houssamzenati/Efficient-GAN-Anomaly-Detection
cd Efficient-GAN-Anomaly-Detection
```

Install requirements (inside virtual env):

```
pip3 install -r requirements.txt
```

## Doing anomaly detection.

Running the code with different options

```
python3 main.py <gan, bigan> <mnist, kdd> run --nb_epochs=<number_epochs> --label=<0, 1, 2, 3, 4, 5, 6, 7, 8, 9> --w=<float between 0 and 1> --m=<'cross-e','fm'> --d=<int> --rd=<int>
# example:
python3 main.py bigan mnist run --nb_epochs=2 --label=0 --w=1 --m=fm --d=1 --rd=4
```
To reproduce the results of the paper, please use w=0.1 (as in the original AnoGAN paper which gives a weight of 0.1 to the discriminator loss), d=1 for the feature matching loss.  

## Updates:  
- 2023/04/20: broken due to tf incompatibiliy with CUDA, use docker instead.
- 2023/04/19: need to upgrade `setuptools` for conda env
- 2022/09/08: tested on Ubuntu 20.04, python 3.8. RTX3090, it works!
