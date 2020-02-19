## Generating simpson faces using Deep Convolutional Generative Adversarial Networks.
### Epoch 1 to 300 in one look:
<p align="center">
  <img width="300" height="300" src="samples/short.gif">
</p>

Dataset: https://www.kaggle.com/kostastokis/simpsons-faces

### How to make the DCGAN work:

There were a lot of tricky details for getting the DCGAN generate some sharp looking pictures. Some of the hacks I used:

* Using 0 as the label for the true class and 1 for fake labels for optimizer. Helps the optimizer to make betterupdates at the first coupleof epochs.
* Smoothing the labels. Instead of 1 i used random numbers in range of [0.7,1.2] and instead of 0 range of [0,0.3]. Prevents the optimizer from reaching loss 0.
* Using noisy labels. I flipped the labels of 5% of the data. 
* Not using any pooling layer. Down sampling is done using stride of 2 in each convolutional layer.
* Using large number of large-sized filters of 5x5. 
* Using the 0.0002 leanring rate for both generator and discriminator.
* Using small batch size of 32. Helps the generator and discriminator to learn at the same pace.

Find out more about the hacks here:
* https://machinelearningmastery.com/how-to-code-generative-adversarial-network-hacks/
* https://medium.com/@utk.is.here/keep-calm-and-train-a-gan-pitfalls-and-tips-on-training-generative-adversarial-networks-edd529764aa9
* https://github.com/soumith/ganhacks

### My favorite generated pictures:
<p align="center">
<img align="center" width="200" height="200" src="samples/ep163.png">
* The generated face looks like the chicken version of the simposons :)
</p>

=========================================================================

<img align="center" width="200" height="200" src="samples/ep141.png">
* It has two mounths :)
=========================================================================

<img align="center" width="200" height="200" src="samples/ep332.png">
* Long fore-head :)
=========================================================================
