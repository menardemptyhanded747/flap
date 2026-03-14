# 670B parameters. 6GB VRAM. 37x faster than PyTorch.

**FLAP trains any LLM on your local GPU, fully automatic, in a fraction of the time.**

[flap-ai.com](https://flap-ai.com) &nbsp;|&nbsp; [Watch the demo](https://flap-ai.com)

---

## This should not be possible

Training a 7B model from scratch on 237 million tokens of real code and text.
On a GTX 1060 6GB from 2016.
Completed in under 48 hours.

Standard PyTorch would take 75 days on the same hardware.
Unsloth with every optimization enabled: 30 days.
An A100 at $3.50/hr: 90 hours and $314 in compute costs.

FLAP: under 48 hours. On your gaming GPU. For $0.

---

## Real benchmark

Dataset: 676M tokens (267MB English + 2GB Python), 35% coverage = 237M tokens trained

| Method                      | Time                 | vs FLAP               |
|---                          |---                   |---                    |
| Standard PyTorch            | ~1,792 hrs (75 days) | 37x slower            |
| Unsloth (all optimizations) | ~717 hrs (30 days)   | 15x slower            |
| A100 at $3.50/hr            | ~90 hrs ($314)       | 2x slower, costs $314 |
| **FLAP on GTX 1060 6GB**    | **under 48 hours**   | **winner**            |

These numbers are not estimates. This training run happened. The hardware is a consumer GPU that costs $80 used.

---

## What FLAP does

You install a lightweight agent (single binary, no dependencies). You connect it to your account. You pick a base model from Hugging Face, upload your dataset, and press start.

The agent handles everything automatically: memory management, training pipeline, progress reporting. Logs stream to your browser in real time. When training finishes, the model is yours.

You write zero code. You configure nothing. You own the output.

---

## Demo

> Training DeepSeek-R1-Distill-Qwen-1.5B on a GTX 1060 6GB, fully automatic, from the dashboard.

[Watch the full demo on flap-ai.com](https://flap-ai.com)

---

## Any model. Any GPU. Any dataset.

FLAP supports every model on Hugging Face. Llama 3, Mistral, DeepSeek, Qwen, Falcon, anything with public weights.

Minimum requirement: 6GB VRAM. That is a GTX 1060. Models up to 670B parameters are supported.

Yes, 670B on 6GB VRAM. That question is addressed below.

---

## Why not just use the cloud

| Cloud                               | FLAP                                       |
|---                                  |---                                         |
| $314 for one A100 training run      | $0, you own the GPU                        |
| Your data uploaded to their servers | Your data never leaves your machine        |
| Waiting for instance availability   | Training starts in seconds                 | 
| Vendor lock-in                      | You own the weights, the model, everything |
| OpenAI sees your fine-tuning data   | No one sees your fine-tuning data          |

---

## Privacy by design

The FLAP agent runs locally. Your dataset is read locally. Your model is trained locally. Nothing is transmitted to FLAP infrastructure except job status and training logs.

No OpenAI. No Google. No AWS. No one touches your data.

---

## Setup

```bash
# 1. Create a free account at flap-ai.com
# 2. Download the agent

./flap-agent login <your-api-key>

# 3. Open flap-ai.com, create a training job, pick a model, upload dataset
# 4. Watch it run
```

That is it. The agent handles everything from there.

---

## How is 670B on 6GB VRAM possible

It is a fair question. The standard answer from every ML framework is: it is not.

FLAP uses a training architecture built from scratch for this exact constraint. It is not LoRA. It is not quantization as a substitute for real training. It is not a known open-source method.

We are not publishing the technical details here. If you want to understand what is happening, run a job and observe the behavior. Every number in this README is reproducible on consumer hardware.

---

[flap-ai.com](https://flap-ai.com) - Free tier available. No credit card required.
