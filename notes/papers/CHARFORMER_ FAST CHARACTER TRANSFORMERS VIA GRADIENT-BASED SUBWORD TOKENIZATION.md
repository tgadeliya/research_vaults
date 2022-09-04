Traditional subword tokenization faces multiple problems:
- Tokenizer dictionary creation procedure doesn't take into account lexical and semantical similarity
- models are brittle to rare words, perturbations (natural and adversarial)
- low-res languages in multilingual models are split into many subwords which impact performance and block cross-lingual transfer
- separate tokenization leads to mismatch between pre-training and downstream performance

Charformer can be a solution:
- have compositionality of character-level representations 
- efficient as subword tokenization 
- end-to-end learning



Algorithm

1) Create sublocks
2) 