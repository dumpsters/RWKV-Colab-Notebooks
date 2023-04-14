# RWKV-Colab-Notebooks

These use [GPT-NeoX's tokenizer](https://github.com/EleutherAI/gpt-neox/blob/b4784bd3f378c7a55f3ab4a259419d21118376cf/tools/preprocess_data.py) and binidx instead of the garbage RAM-intensive tokenizing scripts.

Sample dataset jsonl file:
```json
{"text": "This is a sentence<|endoftext|>"}
{"text": "And this is another one<|endoftext|>"}
{"text": "Don't forget me<|endoftext|>"}
```
The tokenizer will combine all jsonl files into two files the train script will read. Read the outputs of the cells to know what to do.

You should be able to train 169M and 430M fine. 1B5 (RWKV-4-Raven-1B5-v8) will be slow as hell.

---


## RWKV-LorA:
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dumpsters/RWKV-Colab-Notebooks/blob/master/RWKV-LorA.ipynb)

## RWKV-LM:
Soon™

---

Recommended for **RWKV-4-Raven-1B5-v8**:
- `!MAX_JOBS=1 python` instead of `!python`
- micro_bsz  6
- epoch_steps 300
- ctx_len 2048
- grad_cp 1