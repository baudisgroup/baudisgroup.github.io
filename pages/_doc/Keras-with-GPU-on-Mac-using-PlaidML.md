---
title: "Keras with GPU on Mac using PlaidML"
date: 2020-02-04
layout: default
author: Bo Gao
permalink: /howto/Keras-on-Mac.html
excerpt_link: 'http://info.baudisgroup.org/howto/Keras-on-Mac.html'
excerpt_separator: <!--more-->
category: howto
tags:
  - Keras
  - ML
  - OSX
  - software
---

## {{page.title}}

Since Apple and nVidia broke up harshly a few years ago, the official support of all 
nVidia GPUs were stopped. Shortly after, all deep learning frameworks stopped their 
support of GPU acceleration on Mac. Now, there is finally a simple and productive 
solution: using Keras with PlaidML.  

PlaidML provides backends for Keras without requiring CUDA and nVidia hardware. It event
supports Metal on Mac to provide a great improvement of performance. Now we can utilize
our AMD GPU on Mac to drive Keras!

<!--more-->

## Install PlaidML

PlaidML supports Python2, but Python3 is recommended.

1. Setup a virtual environment  

```bash
python3 -m venv plaidml-venv
source plaidml-venv/bin/activate
```

2. Install PlaidML with Keras

```bash
pip install -U plaidml-keras
```

3. Setup PlaidML

```bash
plaidml-setup
```

4. Test

```bash
pip install plaidml-keras plaidbench
plaidbench keras mobilenet
```

## Using Keras with PlaidML

The key step is to set the backend variable.

```python
import os
os.environ[“KERAS_BACKEND”] = “plaidml.keras.backend”
```

Now, Keras is ready to go.

## References

1. [PlaidML github](https://github.com/plaidml/plaidml)
2. [The original blog recommended by Michael](https://www.bignerdranch.com/blog/macos-machine-learning-in-2019/)
3. [Another good guide](https://medium.com/@leonbovett/getting-started-with-keras-on-a-mac-with-blackmagic-egpu-4459bf5128c8)
4. [A simple bechmarking](https://medium.com/@danbrice.datascience/deep-learning-on-a-mac-with-amd-gpu-4be1f18944a)


