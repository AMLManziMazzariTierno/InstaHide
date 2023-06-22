# InstaHide training on CIFAR-100 with ResNet20

## How to run
### Install dependencies
- Create an Anaconda environment with Python3.6
```
conda create -n instahide python=3.6
```
- Run the following command to install dependencies
```
conda activate instahide
pip install -r requirements.txt
```
### Important script arguments
Training configurations:
- `model`: network architecture (default: 'ResNet20')
- `lr`: learning rate (default: 0.1)
- `batch-size`: batch size (default: 128)
- `decay`: weight decay (default: 1e-4)
- `no-augment`: turn off data augmentation 
  
InstaHide configurations:
- `klam`: the number of images got mixed in an instahide encryption, `k` in the paper (default: 4)
- `mode`: 'instahide' or 'mixup' (default: 'instahide')
- `upper`: the upper bound of any coefficient, `c1` in the paper (default: 0.65)
- `dom`: the lower bound of the sum of coefficients of two private images, `c2` in the paper (default: 0.3, *only for Cross-dataset InstaHide*)
  
### Inside-dataset InstaHide:
Inside-dataset Instahide mixes each training image with random images within the same private training dataset. 

For inside-dataset InstaHide training, run the following script:
```
python train_inside.py --mode instahide --klam 4 
```


## References:
[1] [**InstaHide: Instance-hiding Schemes for Private Distributed Learning**](http://arxiv.org/abs/2010.02772), *Yangsibo Huang, Zhao Song, Kai Li, Sanjeev Arora*, ICML 2020
