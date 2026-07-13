# convert-hf-to-gguf

Convert Hugging Face transformer models to the [GGUF](https://github.com/ggml-org/ggml/blob/master/docs/gguf.md) format for use with [llama.cpp](https://github.com/ggml-org/llama.cpp) and compatible inference engines.

## Installation

```sh
pip install convert-hf-to-gguf
```

## Usage

Convert a Hugging Face model directory to GGUF:

```sh
convert-hf-to-gguf /path/to/model-directory
```

Specify the output format (default: auto):

```sh
convert-hf-to-gguf --outtype f16 /path/to/model-directory
```

Download and convert a model directly from Hugging Face Hub:

```sh
convert-hf-to-gguf --remote --outtype q8_0 HuggingFaceTB/SmolLM2-1.7B-Instruct
```

### Options

| Option | Description |
|--------|-------------|
| `--outtype` | Output format: `f32`, `f16`, `bf16`, `q8_0`, `tq1_0`, `tq2_0`, `auto` (default) |
| `--vocab-only` | Extract only the vocabulary |
| `--outfile` | Output file path |
| `--remote` | Read model files remotely from Hugging Face Hub |
| `--mmproj` | Export multimodal projector for vision models |
| `--print-supported-models` | List all supported model architectures |
| `--verbose` | Increase output verbosity |
| `--split-max-size` | Split output into chunks of max size (e.g., `4G`) |

See `--help` for the full list of options.

## Supported models

Convert-hf-to-gguf supports a wide range of model architectures including:
LLaMA, Mistral, Mixtral, Qwen, DeepSeek, Falcon, Gemma, Phi, BERT, Mamba,
GPT-NeoX, StableLM, Command-R, DBRX, OLMo, Grok, and many more.

Run `convert-hf-to-gguf --print-supported-models` for the full list.

## License

MIT
