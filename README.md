# Datasets for Training Conditional StyleGANs
Do you want to train a conditional StyleGAN? While all documentation for generating datasets can be found on the official [StyleGANv3 GitHub](https://github.com/NVlabs/stylegan3), we provide here some commonly used datasets, ready to use. For information on how to train a StyleGAN, please refer to the [guide](https://github.com/NVlabs/stylegan3).

All datasets provided are already formatted correctly with `.png` files of shape $2^n \times 2^n \times c$. The specific datasets and transformations used for them can be found in the following sections. All datasets can be downloaded and used as a `.zip` file. All class information of individual datapoints is found in the `dataset.json` files within the zips.

----------
### MNIST [[1]](#1)
The [MNIST](https://yann.lecun.com/exdb/mnist/) dataset is a classic, containing handwritten digits from 0-9. Since the original dataset has images of shape $28 \times 28$, we adapted the size to $32 \times 32$ using zero-padding. Note that for this dataset, only the train split is contained in the `.zip`.

----------
### AudioMNIST [[2]](#2)
Are simple images too boring for you? [AudioMNIST](https://github.com/soerenab/AudioMNIST) is the solution. This dataset again contains digits from 0-9, but now spoken by 60 different people. In order to use this data in StyleGAN, we transformed the `.wav` files into Mel-Spectrograms of shape $128 \times 128$. Note that since most sounds have different lengths, we had to perform additional transformations, found in `AudioMNIST/transform.ipynb`.
_(Note: You do not need to transform the data again! This is only to show the method.)_ For this dataset, a train/test split has to be done manually.

----------
### CIFAR-10 [[3]](#3)
The [CIFAR-10 dataset](https://www.cs.toronto.edu/~kriz/cifar.html) consists of 10 different classes of images. All images are of shape $32 \times 32 \times 3$ by default, so no special processing is required for this dataset. Note that this CIFAR-10 dataset for conditional StyleGAN training **only** contains the 50,000 training images.

----------
### CIFAR-100 [[3]](#3)
The [CIFAR-100 dataset](https://www.cs.toronto.edu/~kriz/cifar.html) is similar to CIFAR-10, where all images are of shape $32 \times 32 \times 3$. Again, no special processing is required. However, in contrast to CIFAR-10, we now have 100 different classes in the dataset. These classes can be grouped into 20 superclasses. The `dataset.json` file now has a slightly different structure, where each element is as follows: *\[filename, \[coarse_class, fine_class\]\]*. 
For training conditional StyleGANs, you can use either one or both classes, depending on the use case.
Note that again this dataset only contains the train split provided in the original CIFAR-100 dataset.

----------
### ESC-50 [[4]](#4)
The [ESC-50 dataset](https://github.com/karolpiczak/ESC-50) is a collection of 2000 environmental sounds, with 50 seperate classes.
Each audio segment is 5 seconds long. For this dataset the transformations are more substential again, therefore they can be found in `ESC-50/trainsform.ipynb`.
Since StyleGAN can only take square images the long audio files are split into segments and filtered for relevance.
Note that for this dataset the train/ test split has to be done manually!

----------
#### How to Request Datasets
If you think a dataset is missing and could be of use to the broader research community, please open an issue for the dataset in question.

Make sure to include the following information:

- Author & Source
- Download URL or Webpage
- Small description of why it is relevant


#### References:
<a id="1">[1]</a> Y. LeCun, L. Bottou, Y. Bengio, and P. Haffner. "Gradient-based learning applied to document recognition." Proceedings of the IEEE, 86(11):2278-2324, November 1998.<br/>
<a id="2">[2]</a> S. Becker, J. Vielhaben,  M. Ackermann, K. R. Müller, S. Lapuschkin and W. Samek. "AudioMNIST: Exploring Explainable Artificial Intelligence for audio analysis on a simple benchmark." Journal of the Franklin Institute, 361(1), 418-428, January 2024.<br/>
<a id="3">[3]</a> A. Krizhevsky and G. Hinton. "Learning multiple layers of features from tiny images." 2009.<br/>
<a id="4">[4]</a> K. J. Piczak. "ESC: Dataset for Environmental Sound Classification." Proceedings of the 23rd Annual ACM Conference on Multimedia, October 2015.<br/>