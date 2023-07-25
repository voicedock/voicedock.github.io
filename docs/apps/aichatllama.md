# AI chat llama
Llama.cpp based VoiceDock AI chat implementation.
Provides gRPC API for AI chat based on llama.cpp project. Provides download of new model via API.

## Features
* Browse and download AI model (models in ggml format)
* Query-based text generation through AI model
* GPU support
* Fast performance on cpu

## Installation
Create directories for model data and configuration:
``` bash
mkdir dataset
mkdir config
```
Create a `config/aichatllama.json` configuration file or download an example configuration:
``` bash
curl -o config/aichatllama.json https://raw.githubusercontent.com/voicedock/aichatllama/main/config/aichatllama.json
```

=== "Docker (on CPU)"

    ``` bash
    docker run --rm \
        -v "$(pwd)/config:/data/config" \
        -v "$(pwd)/dataset:/data/dataset" \
        -p 9999:9999 \
        ghcr.io/voicedock/aichatllama:latest aichatllama
    ```

=== "Docker (on GPU)"
OpenCL, Nvidia CUDA
    ``` c++
    docker run --rm \
        -v "$(pwd)/config:/data/config" \
        -v "$(pwd)/dataset:/data/dataset" \
        -e LLAMA_GPU_LAYERS=2 \
        --runtime=nvidia --gpus all \
        -p 9999:9999 \
        ghcr.io/voicedock/aichatllama:gpu aichatllama
    ```

## Configuration
[See on Github](https://github.com/voicedock/aichatllama).
