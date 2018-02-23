# Paper

* **Title:** SeqGAN Sequence Generative Adversarial Nets with Policy Gradient
* **Authors:** Lantao Yu, Weinan Zhang, Jun Wang, Yong Yu
* **arXiv link:** https://arxiv.org/abs/1609.05473

# TL;DR

* The paper describes a method to train a Generative Adversarial Network(GAN) to generate discrete sequential data (eg. text, music) by using an RNN as a generator and policy gradients for training, to account for the discreteness of the data.

# Motivation

* Although LSTM is widely used for generating sequential data, [Bengio et al. 2015](https://arxiv.org/abs/1506.03099) showed the exposure bias problem while generating with an LSTM at test time and suggested a curriculum learning method Scheduled Sampling for training to overcome it (Note: They won the MSCOCO image captioning challenge 2015 with this setup)
* However, [Huszar 2015](https://arxiv.org/abs/1511.05101) showed theoretically that Scheduled Sampling is an inconsistent strategy i.e. it does not minimize the KL divergence between real distribution and the learned distribution.
* The paper, hence, aims to train a GAN for text generation.

# Why not use vanilla GAN?

* Ian Goodfellow, the inventor of GAN, explains in [this reddit comment](https://www.reddit.com/r/MachineLearning/comments/40ldq6/generative_adversarial_networks_for_text/cyyp0nl/) why vanilla GAN does not work with text data.
* In addition, the discriminator can only give likelihood of an entire sequence and it is not exactly clear how to balance the likelihood for a partial sequence.

# Method
