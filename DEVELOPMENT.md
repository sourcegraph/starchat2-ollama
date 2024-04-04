## Install huggingface-cli and hf_transfer

```
python -m pip install huggingface_hub
python -m pip install hf_transfer
huggingface-cli login
```

## Download the model

```
HF_HUB_ENABLE_HF_TRANSFER=1 huggingface-cli download 'HuggingFaceH4/starchat2-15b-v0.1'
```

## Download and build llama.cpp

```
git clone https://github.com/ggerganov/llama.cpp
cd llama.cpp/
make
python3 -m pip install -r requirements.txt
```

## Convert the .safetensors model to .gguf

python convert.py --outtype f16 --ctx 4096 models/<INSERT_YOUR_FOLDER_NAME_HERE> 

## Produce quantized variants

./llama.cpp/quantize ./starchat2-15b-v0.1-f16.gguf ./starchat2-15b-v0.1-f16_Q4_0.gguf Q4_0
./llama.cpp/quantize ./starchat2-15b-v0.1-f16.gguf ./starchat2-15b-v0.1-f16_Q8_0.gguf Q8_0

## Produce ollama models

```
ollama create -f starchat2-15b-v0.1-f16.Modelfile slimsag/starchat2:15b-v0.1-f16
ollama create -f starchat2-15b-v0.1-f16_Q4_0.Modelfile slimsag/starchat2:15b-v0.1-f16-q4_0
ollama create -f starchat2-15b-v0.1-f16_Q8_0.Modelfile slimsag/starchat2:15b-v0.1-f16-q8_0
```

## Test the models

```
ollama run slimsag/starchat2:15b-v0.1-f16-q8_0 'How can I write a simple Python HTTP server that response to GET / with "hello world"?'
ollama run slimsag/starchat2:15b-v0.1-f16-q4_0 'How can I write a simple Python HTTP server that response to GET / with "hello world"?'
```






brew install git-lfs
git lfs install
huggingface-cli lfs-enable-largefiles .


git clone https://huggingface.co/HuggingFaceH4/starchat2-15b-v0.1
