While considering choosing model to use, we have multiple dimensions to choose
- architecture
- pre-training objective
one of this directions
This paper research how we should choose over this directions
example, bounding a model by bidirectional context (or the future) (ie.., span corruption) makes the task easier and becomes more akin to fact completion.


We then disentangle the architecture from the self-supervision scheme. While it might be a common misconception, as previously noted in Raffel et al. (2019), that a pre-trained model is strongly characterized by its backbone architecture (e.g., decoder-only vs. encoder-decoder), **we find that the choice of the denoiser has significantly more impact**. MoD supports either backbone, similar to how T5’s span corruption may be trained with a decoder-only model.