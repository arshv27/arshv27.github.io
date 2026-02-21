---
layout: page
title: RoPE + GQA for Transformers
description: Implemented Rotary Positional Embeddings and Grouped-Query Attention in a GPT-style Transformer
importance: 1
category: work
---

- Implemented Rotary Positional Embeddings and Grouped-Query Attention in a GPT-style Transformer, with Key-Value caching and causal masking.
- Benchmarked attention latency across sequence lengths and head configurations, reducing validation loss by >10% over a minGPT baseline and improving throughput/memory behavior.