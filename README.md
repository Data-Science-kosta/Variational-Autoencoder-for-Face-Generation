# Variational-Autoencoder-for-Face-Generation
This repository contains Keras implementation of the Variational Autoencoder for face generation.
## DATASET
The model was trained on [CelebA](https://www.kaggle.com/jessicali9530/celeba-dataset) dataset. It contains 202600 images of human faces, which are labeled with attributes (such as smiling, young, male, eyeglasses, ...).
## RESULTS
Following results are for the model trained on images of size 128x128.
### Reconstructing faces
![reconstructing faces](https://github.com/Data-Science-kosta/Variational-Autoencoder-for-Face-Generation/blob/master/results/20.png)
The images blurry, but that is expected for VAE because it averages squared error across pixels.
### Generating new faces
New faces are generated by sampling the vector of the latent space from the prior distribution and passing it through the decoder.
![generating faces](https://github.com/Data-Science-kosta/Variational-Autoencoder-for-Face-Generation/blob/master/results/21.png)
### Analysis of the distribution of the latent space
Posterior distribution should be close to standard normal distribution, since the KL divergence in the loss function pushes posterior distribution to be close to the prior (which is standard normal distribution). We can not visualize 200 dimensional distribution, so the t-SNE algorithm is performed to reduce the dimensions to 2. 
2D Distribution evaluated on 20 000 images is plotted on the right, and its histogram is presented on the left: <br />
![2D distribution](https://github.com/Data-Science-kosta/Variational-Autoencoder-for-Face-Generation/blob/master/results/31.png) <br />
Since it is assumed that covariance matrix of the posterior distribution is diagonal, each dimension should be close to normal. <br />
Distribution of the first 30 dimensions of the posterior distribution, evaluated on the 20 000 images, are shown with blue color and standard normal distribution is show with red:<br />
![30 dims](https://github.com/Data-Science-kosta/Variational-Autoencoder-for-Face-Generation/blob/master/results/22.png) <br />
