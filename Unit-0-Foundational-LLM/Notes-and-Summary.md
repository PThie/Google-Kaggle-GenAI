# Notes and Summary on Foundational LLM (Unit 0)

~ NOTE: still in progress ~

## Introduction

- Many models are built on the transformer architecture
- Originally a transformer has two parts: encoder and decoder
- Encoder: processes the input sequence and generates a context vector
- Decoder: takes the context vector and generates the output sequence
- Encoder and decoder consist of multiple (hidden) layers

## Process from input to output

- Input text &rarr; input embedding &rarr; positional encoding &rarr; multiply layers (multi-head attention, feed-forward, and layer normalization and residual connections)

### Multi-head attention and self-attention

- Self-attention = determines the relationship between words in a sentence using queries, keys, and values

- Multi-head attention = multiple self-attention mechanisms in parallel, allowing the model to focus on different parts of the input sequence simultaneously
- Allows the model to handle more complex language patterns

### Layer normalization and residual connections ("Add and Norm")

### Feed-forward layer

## Improving the model

### Mixture of Experts

## Steps of training a model

### Pre-training

- Model learns the basic elements of language

### Fine-tuning

- Train the model further on specific tasks with more targeted data
- Different techniques (e.g.): Supervised fine-tuning, Reinforcement learning from human feedback (RLHF)

## Adapting to new tasks (without re-training)

- You don't want to fine-tune the model for every task &rarr; resource intensive

### Parameter Efficient Fine-tuning (PEFT)

- Train only a small part of the model (few parameters), while keeping the rest of the model frozen &rarr; fine-tuning becomes faster



