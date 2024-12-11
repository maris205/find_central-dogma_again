# Find central dogma again
Multilingual transfer ability, which reflects how well models fine-tuned on one source
language can be applied to other languages, has been well studied in multilingual pre-trained
models. However, the existence of such capability transfer between natural language and gene
sequences/languages remains underexplored.This study addresses this gap by drawing inspiration
from the sentence-pair classification task used for evaluating sentence similarity in natural
language. We constructed two analogous tasks: DNA-pair classification(DNA sequence similarity)
and DNA-protein-pair classification(gene coding determination). These tasks were designed to
validate the transferability of capabilities from natural language to gene sequences. Even a
small-scale pre-trained model like GPT-2-small, which was pre-trained on English, achieved an
accuracy of 78% on the DNA-pair classification task after being fine-tuned on English
sentence-pair classification data(XTREME PAWS-X). While training a BERT model on
multilingual text, the precision reached 82%.On the more complex DNA-protein-pair
classification task, however, the model's output was barely distinguishable from random
output.Experiments suggest that there may be a capability transfer from natural language to
genetic language, but further task testing is needed to confirm this.


# experiment result

| base model     | pretrain | finetune | test-en | test-fr | test-de | test-zh | test-dna |
|----------------|----------|----------|---------|---------|---------|---------|----------|
| gpt2-small     | en       | en       | 0.92    | 0.74    | 0.73    | 0.61    | **0.78** |
| gpt2-medium    | en       | en       | 0.92    | 0.80    | 0.76    | 0.62    | 0.55     |
| gpt2-large     | en       | en       | 0.94    | 0.81    | 0.79    | 0.66    | 0.63     |
| bert           | en       | en       | 0.91    | 0.77    | 0.73    | 0.52    | 0.54     |
| bert           | multilan | en       | 0.94    | 0.86    | 0.83    | 0.77    | **0.82** |
| gpt2-small-1   | en+DNA   | en       | 0.90    | 0.74    | 0.72    | 0.59    | 0.48     |
| gpt2-small-2   | en+DNA   | en       | 0.76    | 0.59    | 0.60    | 0.56    | 0.60     |



* dna_150.json, dna pair data
* dna_protein_150.json, dna protein pair data
* gpt2_small_pretrain_en_finetune_en.ipynb , code for gpt2 small
* gpt2_medium_pretrain_en_finetune_en.ipynb, code for gpt2 medium
* gpt2_large_pretrain_en_finetune_en.ipynb, code for gpt2 large
* bert_pretrain_en_finetune_en.ipynb, code for bert base
* bert_multi_pretrain_en_finetune_en.ipynb, code for bert multi language
* gpt2_small_pretrain_en_dna_finetune_en.ipynb, code for gpt2-small-2

# paper
```json
@misc{liang2024linguistsbetterunderstanddna,
      title={Can linguists better understand DNA?}, 
      author={Wang Liang},
      year={2024},
      eprint={2412.07678},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2412.07678}, 
}
```
