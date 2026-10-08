---
license: apache-2.0
base_model:
  - Qwen/Qwen3.5-2B
  - Qwen/Qwen3.5-0.8B
base_model_relation: quantized
library_name: gguf
tags:
  - gguf
  - mirror
  - llama.cpp
---

# Hugrheim SLM models

Unmodified mirror of two GGUF files, kept by HugrheimLABS so that the Hugrheim Training Android app can download its certified on-device models from a project repository. Nothing in this repository was retrained, re-quantized or edited.

## Files

| File | Base model | Quantization | Mirrored from (repository @ commit) | Bytes | SHA-256 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `Qwen_Qwen3.5-2B-Q4_K_M.gguf` | [Qwen/Qwen3.5-2B](https://huggingface.co/Qwen/Qwen3.5-2B) | Q4_K_M | [`bartowski/Qwen_Qwen3.5-2B-GGUF`](https://huggingface.co/bartowski/Qwen_Qwen3.5-2B-GGUF) @ `7d26695454df6de5fbcce2e58681e62dae06ce43` | 1396198496 | `57a1085840f497d764a7fc5d346922dbde961efb54cc792ea81d694fd846a1d8` |
| `Qwen_Qwen3.5-0.8B-Q4_K_M.gguf` | [Qwen/Qwen3.5-0.8B](https://huggingface.co/Qwen/Qwen3.5-0.8B) | Q4_K_M | [`bartowski/Qwen_Qwen3.5-0.8B-GGUF`](https://huggingface.co/bartowski/Qwen_Qwen3.5-0.8B-GGUF) @ `f36b1ea49a332ede8fe5f389bbf5b3575ef71f48` | 579615840 | `fb044e93939a70469c905781334f5de1e6c8b608ced6cbc8c9249bd4127d9526` |

Each file is byte-for-byte identical to the one at the commit listed. The app checks size and SHA-256 against the values compiled into it and refuses any other file, so a file in this repository is only ever replaced together with a new app build.

The vision projector (`mmproj-*.gguf`) of the original repositories is not mirrored: the app uses text only.

## Usage

These are standard GGUF files and load in any recent build of [llama.cpp](https://github.com/ggml-org/llama.cpp):

```bash
llama-cli -m Qwen_Qwen3.5-0.8B-Q4_K_M.gguf -p "Ciao"
```

To verify a download:

```bash
sha256sum Qwen_Qwen3.5-2B-Q4_K_M.gguf
```

## License

The models are released by the Qwen team under the Apache License 2.0; the license text is in [`LICENSE`](LICENSE). The quantizations are by [bartowski](https://huggingface.co/bartowski). All credit for the models belongs to their authors; HugrheimLABS only redistributes them, unchanged.
