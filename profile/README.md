# UltiMed

> [!WARNING]
> **Release in progress.** UltiMed v2 is being released right now. As long as this notice is here, repositories, links and numbers are still being changed, and some of the v2 links below may not work yet.

UltiMed is an open project for **French medical speech recognition**, built on a single consumer GPU. It produces a synthetic speech dataset of medical dictation (drug names and dosages, medical dictionary terms, clinical notes, radiology reports, acronyms), fine-tunes parakeet-ultra (a post-trained NVIDIA `parakeet-tdt-0.6b-v3`) on it, exports the result to ONNX so it runs locally (including in the browser), and ships regex rules that fix the errors the model still makes. Everything is published: data, code, weights and rules.

> [!NOTE]
> **v3 is already planned, and it will be multilingual.** v1 and v2 are French only.

## Current release: v2

| | |
|---|---|
| Dataset | [Olicorne/UltiMed-ASR-FR-v2](https://huggingface.co/datasets/Olicorne/UltiMed-ASR-FR-v2) on Hugging Face |
| Model | [Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v2-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v2-onnx) on Hugging Face (ONNX, fp32 / fp16 / int8 / w4a8) |
| Dataset scripts | [UltiMed-ASR-FR-v2-scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v2-scripts): text generation, speech synthesis, quality control, release |
| Training scripts | [UltiMed-ASR-FR-v2-NeMo_training_scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v2-NeMo_training_scripts): the NeMo fork used to fine-tune the model |
| Error fixes | [UltiMed-ASR-FR-v2-regex-fixes](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v2-regex-fixes): regex rules and lookup tables that fix the model's remaining mistakes |

## Use it

| | |
|---|---|
| In the browser | [parakeet_web](https://github.com/thiswillbeyourgithub/parakeet_web): local transcription in a web page, with a medical mode that uses the UltiMed model and rules |
| On the desktop | [Plumed](https://github.com/PlumedOrg/Plumed): a dictation app that uses the UltiMed model and rules |

## Related models

| | |
|---|---|
| [Olicorne/parakeet-tdt-0.6b-v3-ultra-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-ultra-onnx) | Parakeet Ultra in ONNX: moondream's post-trained `parakeet-tdt-0.6b-v3`, general purpose, which the UltiMed model is fine-tuned from |
| [Olicorne/parakeet-tdt-0.6b-v3-redux-UltiMed-experimental-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-redux-UltiMed-experimental-onnx) | an experimental weight blend of the parakeet redux model with UltiMed v1, not a proper fine-tune |

## Previous release: v1 (obsolete)

Kept for reference and reproducibility. Use v2 instead.

| | |
|---|---|
| Dataset | [Olicorne/UltiMed-ASR-FR-v1](https://huggingface.co/datasets/Olicorne/UltiMed-ASR-FR-v1) |
| Model | [Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v1-onnx](https://huggingface.co/Olicorne/parakeet-tdt-0.6b-v3-ultra-UltiMed-v1-onnx) |
| Dataset scripts | [UltiMed-ASR-FR-v1-scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v1-scripts) |
| Training scripts | [UltiMed-ASR-FR-v1-NeMo_training_scripts](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v1-NeMo_training_scripts) |
| Speech synthesis setup | [UltiMed-ASR-FR-v1-Voxtral](https://github.com/UltiMed-Org/UltiMed-ASR-FR-v1-Voxtral): Docker setup for the Voxtral TTS used to voice v1 |
