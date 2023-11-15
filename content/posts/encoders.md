---
title: "Inside the Transformer: Encoders"
date: 2023-11-15
# weight: 1 # To pin the post 
# aliases: ["/first"]
tags: ["background"]
# author: "Me"
showToc: false
# TocOpen: false
math: true
draft: true # Does not add this page when building with `hugo`
hidemeta: false # Hide the metadata
comments: false
# description: "BERT, T5, all transformer encoders share some common parts. Let me show you."
# canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs https://highlightjs.org/
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true # Show the Home > Posts tab to go back
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
# UseHugoToc: true
---

BERT, T5, essentially all transformer encoders share common parts. Let me show you. This is not the most common way to approach someone, 
but deeply it becomes a narrative. Something all want to do.

> As usual, when seein deep learning problems approach them thinking about matrix multiplications.

![encoder](/images/encoder.svg#center)

Nothing else to explain, let me show

## The Attention Mechanism

The transformer encoder uses something called the attention mechanism.

$$
Z=\text{Softmax}\left(\frac{QK^T}{\sqrt{d^k}}\right)V
$$

In code that looks something like this:

```python
import torch
import torch.nn.functional as F
# Perform matrix multiplication between Q and K
scores = torch.bmm(query, key.transpose(1, 2))
# Scale the scores
scale = key.size(1) ** 0.5  # Square root of the dimension of the querie
scores = scores / scale
# Apply softmax
attn = F.softmax(scores)
# Compute the weighted combination of values based on the attention scores calculated
attn_output = torch.bmm(attn, value)
```

The most important part to remember is that

## Self-attention

The most basic way of seeing self-attention is to comput
