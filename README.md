# LSTMem: Hierarchical Long Short-Term Online Memory for Large Language Models

[![arXiv](https://img.shields.io/badge/arXiv-2609.33268-b31b1b.svg)](https://arxiv.org/abs/2609.33268)

This is the official repository of LSTMem. The code, training data and model weights are being
prepared and will be released here (see the TODO list below).

## Overview

LSTMem is an LSTM-inspired online memory for a frozen large language model. Each layer of the
backbone gets two matrix-valued states: a cell state that accumulates the history and a hidden
state whose readouts correct the backbone's attention. Input and forget gates control what the
cell stores, while an output gate separately controls what the cell exposes through the hidden
state. Memory is also connected across depth: hidden states propagate forward from layer to layer,
and at the end of every history block, block-end feedback uses the reconstruction gradients of
higher layers to refine the cell states of lower layers before the hidden states are rebuilt from
shallow to deep layers.

## TODO

- [ ] **Code**: the LSTMem model, two-stage training, evaluation on MemoryAgentBench, LoCoMo, HotpotQA, IFEval and GPQA-Diamond, and an interactive chat demo
- [ ] **Dataset**: training data for both stages (QASPER episodes for Stage 1, the synthetic Long dataset for Stage 2)
- [ ] **Weights**: trained LSTMem adapters for Qwen3-4B-Instruct-2507, Qwen3-8B and SmolLM3-3B

## Citation

```bibtex
@article{shi2026lstmem,
  title   = {{LSTMem}: Hierarchical Long Short-Term Online Memory for Large Language Models},
  author  = {Shi, Xianglong and Yang, Ruijie and Zhao, Sirui and Yin, Shukang and Bian, Zihao and Yi, Tinghao and Chen, Enhong},
  journal = {arXiv preprint arXiv:2609.33268},
  year    = {2026}
}
```

## Acknowledgements

LSTMem builds on [δ-mem](https://github.com/declare-lab/delta-Mem).
