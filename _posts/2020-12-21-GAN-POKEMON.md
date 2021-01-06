---
title: 'GANs & Pokemons'
date: 2020-12-21
permalink: /posts/2020/12/GAN-POKEMON/
tags:
  - GAN
  - Pokemon
  - Deep Learning
---

**What is a Generative Adversarial Network (GAN) ?**
======

The concept of GAN's originate from this paper [here](https://arxiv.org/abs/1406.2661) by Ian J. Goodfellow and al. in 2014.
**Intuition about GAN's**
------

*What are we trying to do when training a neural network ?* \
When training a neural network we make an important assumption that if we successfully learn a mapping of our data space, we will then be able to leverage this learning to infer about the future distribution of unseen data and thus make accurate prediction on this new data. \
GAN's try to do that by playing a two-player game where the two agents by competing against one another are able to learn a mapping of the data distribution. This is great when we have data and no labels that allow us to correct our model when it's wrong. \

Let's dissect the title of this method : 
* **Generative** : this is because the model outputs a creation of it's own. Most tasks in Deep learning involves feeding something to a model (image, text, audio etc...) and receiving an output of the model (Class label, Number, text etc..). \
GAN's are Generative because when you feed them images they will also output images for example.
* **Networks** : A GAN involves two network, first a **Generator**, which will receive random noisy data as impute and output an Image. And a **Discriminator** which receives images as input, it's role is to predict if the image received is a real image (coming from your dataset) or a fake image (created by your Generator). \
These two will most of the time be Neural Networks.

* **Adversarial** : Finally Adversarial because when trained, these two will compete with one another. The Generator will try to create better and better images to try and fool the Discriminator. And inversely, the Discriminator will become a better and better classifier that predicts more accurately which images are real or fake.

**How does it learns ?**
------

$\underset{G}min\;\underset{D}max\;V(D,G) = E_{x\sim p_{data}}(x)[log D(x)] + E_{z \sim p_z}(z)[log(1-D(G(z)))]$ \

the equation above define the learning of these two networks as a **two-player minimax game** with value function V(G,D). \
In other words, we train the Discriminator to maximize it's probability to assign the correct label to the data it receives(that's $log D(x)$) and simultaneously we train the Generator to "fool" the Discriminator as best as it can (that's the $log(1-D(G(z)))$) meaning it tries to minimize D's accuracy. 

In practice the networks are most often trained using Gradient Descent.

**How did we improve GANs ?**
======

**GANs unstability**
------

**Improving the Networks**
------

**Improving the loss**
------

**GANs & Pokemons**
======