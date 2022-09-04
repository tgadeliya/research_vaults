Use combination of determenistic segmentation (BPE) and probabilistic to obtain more robust multilingual segmentation and hence better zero-shot performance on cross-lingual transfer from english to low-resource languages after fine-tuning
![[Pasted image 20220805093013.png]]
Three losses:
- determenistic CE loss (BPE)
- probabilistic CE loss (BPE-Dropout)
- consistency loss between two above losses


For BPE use BPE-dropout as prob.segm., for ULM - ULM-sample when sample from candidate scored by LM


comparing to subword regularization - methods when we sample different segmentation of sentence during the training