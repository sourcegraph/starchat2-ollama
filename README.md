# Starchat2 for Ollama ([view on Ollama](https://ollama.com/slimsag/starchat2))

Lets you test/use [Starchat2 (15b v0.1)](https://huggingface.co/HuggingFaceH4/starchat2-15b-v0.1) models using [Ollama](https://ollama.com/).

## Try it out

```
ollama run slimsag/starchat2:15b-v0.1-f16-q4_0 'How can I write a simple Python HTTP server that response to GET / with "hello world"?'
```

## Quantized models

The following models are available:

* `slimsag/starchat2:15b-v0.1-f16-q4_0` (recommended)
* `slimsag/starchat2:15b-v0.1-f16-q8_0`
* `slimsag/starchat2:15b-v0.1-f16` (non-quantized)

## Development

To produce the models see [DEVELOPMENT.md](./DEVELOPMENT.md)
