This work inspired by MAE approach, which use MLM to pretrain models

The main problem authors tries to solve is  [[vocabulary bottleneck]]  - there is a bottleneck in two locations: 
- at level of the encoding of the inputs
- at the level of estimating the problability distribution over the vocabulary

This especially help in multiingual scenario, when we have huge dictionaries
Authors propose rethink LM as visual recognition task and pre-train model on the same data as BERT

PIXEL can handle char-level noise  and word-level noise

![[Pasted image 20220805085521.png]]

PIXEL-base is a 112M parameter ViT-MAE architecture with a 12-layer ViT encoder (86M) and an 8-layer Transformer decoder (26M). The same patching procedure is used as ViT

Span masking
PIXEL uses span masking with a 25% masking ratio as outlined in Algorithm 1, which masks spans of up to S = 6 consecutive image patches with a dynamic number of unmasked patches left between them.