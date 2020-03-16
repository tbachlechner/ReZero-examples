# ReZero-examples

This repo contains tutorials/examples demonstrating the power of the ReZero architecture, see the [paper](https://arxiv.org/pdf/2003.04887.pdf).

The official ReZero repo is [here](https://github.com/majumderb/rezero).

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
