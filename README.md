# ReZero-examples

This repo contains examples demonstrating the power of the ReZero architecture, see the [paper](https://arxiv.org/pdf/2003.04887.pdf).

The official ReZero repo is [here](https://github.com/majumderb/rezero).

- [ReZero speeds up superconvergence](https://github.com/tbachlechner/ReZero-Superconvergence/blob/master/Faster_SuperC.ipynb)

- [ReZNet - Faster ResNet training via ReZero](https://github.com/tbachlechner/ReZero-examples/blob/master/ReZNet-6x_faster_ResNet_training_via_ReZero.ipynb)
<p align="center">
<img src=./Plots/ResNet56_error_2.png  alt="ResNet56_error" width="450"/>
</p>

Final valid errors: Vanilla - 7.74. FixUp - 7.5. ReZero - 6.38,  [see](https://github.com/tbachlechner/Fixup) .

- [Training 128 layer ReZero Transformer on WikiText-2 language modeling](https://github.com/tbachlechner/ReZero-examples/blob/master/ReZero-Deep_Fast_Transformer.ipynb)
- [Training 10,000 layer ReZero fully connected network on CIFAR-10](https://github.com/tbachlechner/ReZero-examples/blob/master/ReZero-Deep_Fast_NeuralNetwork.ipynb)

# Contribute

If you find ReZero or a similar architecture improves the performance of your application, you are invited to share a demonstration here.

# Install

To install ReZero via pip use ```pip install rezero```

# Usage
We provide custom ReZero Transformer layers (RZTX).

For example, this will create a Transformer encoder:
```py
import torch
import torch.nn as nn
from rezero.transformer import RZTXEncoderLayer

encoder_layer = RZTXEncoderLayer(d_model=512, nhead=8)
transformer_encoder = nn.TransformerEncoder(encoder_layer, num_layers=6)
src = torch.rand(10, 32, 512)
out = transformer_encoder(src)
```

# Citation
If you find `rezero` useful for your research, please cite our paper:
```BibTex
@inproceedings{BacMajMaoCotMcA20,
    title = "ReZero is All You Need: Fast Convergence at Large Depth",
    author = "Bachlechner, Thomas  and
      Majumder, Bodhisattwa Prasad
      Mao, Huanru Henry and
      Cottrell, Garrison W. and
      McAuley, Julian",
    booktitle = "arXiv",
    year = "2020",
    url = "https://arxiv.org/abs/2003.04887"
}
```
