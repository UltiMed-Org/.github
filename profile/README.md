# UltiMed

[Version française](https://github.com/UltiMed-Org/.github/blob/main/profile/README.fr.md)

> [!IMPORTANT]
> **Want faster improvements?** This project is entirely self-funded on my minimum-wage salary, and every training run competes for a single consumer GPU. If you or your organisation can donate an **RTX 5090**, or the money to buy one second-hand, it would directly speed up the next versions of the dataset and the fine-tuned models. Reach out via [olicorne.org](https://olicorne.org) or open an issue on one of the repositories.

UltiMed is a project by [Olivier Cornelis](https://olicorne.org) to make medical audio dictation ubiquitous and free. It produces a synthetic speech dataset of French medical dictation (drug names and dosages, medical dictionary terms, clinical notes, radiology reports, acronyms), fine-tunes parakeet-ultra (a post-trained NVIDIA `parakeet-tdt-0.6b-v3`) on it, exports the result to ONNX so it runs locally (including in the browser), and ships regex rules that fix the errors the model still makes. Everything is published: data, code, weights and rules.

> [!WARNING]
> **v3 is already planned, and it will be multilingual.** v1 and v2 are French only.

## Current release: v2

| What | Where |
|---|---|
| Dataset | [Olicorne/UltiMed-ASR-FR-v2](https://huggingface.co/datasets/Olicorne/UltiMed-ASR-FR-v2) on Hugging Face |
| Model | [Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v2-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v2-onnx) on Hugging Face (ONNX, fp32 / fp16 / int8 / w4a8) |
| Small model (experimental) | [Olicorne/parakeet-tdt-0.6b-v3-redux-UltiMed-experimental-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-redux-UltiMed-experimental-onnx): the 2-bit parakeet redux model with the UltiMed v2 fine-tuning change added, about 3 times smaller than the int8 model, CPU only |
| Dataset scripts | [UltiMed-ASR-FR-v2-scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v2-scripts): text generation, speech synthesis, quality control, release |
| Training scripts | [UltiMed-ASR-FR-v2-NeMo_training_scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v2-NeMo_training_scripts): the NeMo fork used to fine-tune the model |
| Speech synthesis setup | [UltiMed-ASR-FR-v2-Voxtral](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v2-Voxtral): the Voxtral TTS harness (vLLM + patched vllm-omni) where the five v2 voices were built and served |
| Error fixes | [UltiMed-ASR-FR-v2-regex-fixes](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v2-regex-fixes): regex rules and lookup tables that fix the model's remaining mistakes |

## Use it

| Where | App |
|---|---|
| In the browser | [parakeet_web](https://github.com/thiswillbeyourgithub/parakeet_web): local transcription in a web page, with a medical mode that uses the UltiMed model and rules |
| On the desktop | [Plumed](https://github.com/PlumedOrg/Plumed): a dictation app, fork of [Murmure](https://github.com/Kieirra/murmure), that uses the UltiMed model and rules |

## Related models

| Model | What it is |
|---|---|
| [Olicorne/parakeet-tdt-0.6b-v3-ultra-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-ultra-onnx) | Parakeet Ultra in ONNX: moondream's post-trained `parakeet-tdt-0.6b-v3`, general purpose, which the UltiMed model is fine-tuned from |

## Previous release: v1 (obsolete)

Kept for reference and reproducibility. Use v2 instead.

| What | Where |
|---|---|
| Dataset | [Olicorne/UltiMed-ASR-FR-v1](https://huggingface.co/datasets/Olicorne/UltiMed-ASR-FR-v1) |
| Model | [Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v1-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v1-onnx) |
| Dataset scripts | [UltiMed-ASR-FR-v1-scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v1-scripts) |
| Training scripts | [UltiMed-ASR-FR-v1-NeMo_training_scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v1-NeMo_training_scripts) |
| Speech synthesis setup | [UltiMed-ASR-FR-v1-Voxtral](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v1-Voxtral): Docker setup for the Voxtral TTS used to voice v1 |
