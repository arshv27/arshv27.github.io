---
layout: page
title: LoRA for Efficient LLM Fine-Tuning
description: Implemented LoRA for GPT-2 by injecting trainable low-rank adapters into attention layers
importance: 2
category: work
---

- Implemented LoRA for GPT-2 by injecting trainable low-rank adapters into attention layers while freezing base model weights.
- Achieved ~2% higher accuracy than full fine-tuning while updating <5% of parameters, benchmarking convergence and performance across multiple LoRA ranks.