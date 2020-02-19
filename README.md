## Generating simpson faces using Deep Convolutional Generative Adversarial Networks.

<p align="center">
  <img width="300" height="300" src="samples/short.gif">
</p>

Dataset: https://www.kaggle.com/kostastokis/simpsons-faces

There were a lot of tricky details for getting the DCGAN generate some sharp looking pictures. Some of the hacks I used:

* Using 0 as the label for the true class and 1 for fake labels.
* Smoothing the labels. Instead of 1 i used random numbers in range of [0.7,1.2] and instead of 0 range of [0,0.3].
* Using noisy labels. I flipped the labels of 5% of the data. 
* Not using any pooling layer. Down sampling is done using stride of 2 in each convolutional layer.
* Using large filters of 5x5.
* Using the 0.0002 leanring rate for both generator and discriminator.
* Using small batch size of 32.

Read the code for other hacks. Also, find out more about the hacks here:
* https://machinelearningmastery.com/how-to-code-generative-adversarial-network-hacks/
* https://medium.com/@utk.is.here/keep-calm-and-train-a-gan-pitfalls-and-tips-on-training-generative-adversarial-networks-edd529764aa9
* https://github.com/soumith/ganhacks

