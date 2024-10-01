# Datasets for training conditional StyleGANs
Do you want to train a conditional StyleGAN? While all documentation for generating Datasets can be found on the official [StyleGANv3 Github](https://github.com/NVlabs/stylegan3), we provide here some commonly used datasets, ready to use.
For information on how to train a StyleGAN please refer to the [guide](https://github.com/NVlabs/stylegan3).

All datasets provided are already formatted correctly with `.png`-files of shape $2^n\times 2^n \times c$.
The specific datasets and transformations used for them can be found in the following sections.
All datasets can be downloaded and used as a `.zip`-file.

----------
### MNIST
The [MNIST](https://yann.lecun.com/exdb/mnist/) dataset is a classic, containing handwritten digits from 0-9.
Since the original dataset has images of shape $28\times 28$ we adapted the size to $32\times 32$ using 0-padding.
All class information of individual images is found in `dataset.json`.

----------
### AudioMNIST
Is simple images too boring for you? [AudioMNIST](https://github.com/soerenab/AudioMNIST) is the solution. This dataset again conatins digits from 0-9, but now spoken by 60 different people.
In order to use this data in StyleGAN we transfromt the `.wav` files into Mel-Spectrograms of shape $128\times 128$.
Note that since most sounds have different lengths we have to do additional transformations, found in `AudioMNIST/transformations.ipynb`.

----------
### More Datasets coming soon!