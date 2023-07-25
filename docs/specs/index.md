# API proto specification

VoiceDock provides a modular approach. For each module type, the [gRPC](https://grpc.io/) API interaction
specification is described in the [Protocol Buffers](https://protobuf.dev/) format.

The VoiceDock concept is aimed at creating a universal and simple industrial-grade API that solves problems
in the field of creating digital assistants, human interaction with artificial intelligence and related areas.

The mission of VoiceDock is to quickly adapt new research by scientists for use in production.
So that previously written code can quickly switch to using the new implementation.
It is enough just to create an implementation of the gRPC API module for the new algorithm.

## API Overview

* [STT API](#stt-api) - speech to text. (ASR - Automatic Speech Recognition).
* [TTS API](#tts-api) - text to speech.
* [AI Chat API](#ai-chat-api) - text interaction with artificial intelligence

## STT API
The API receives an audio stream in PCM format (int 16 bit little-endian bytes) and returns a stream of recognized
text tokens.

| proto                  | [stt_api.proto](https://github.com/voicedock/voicedock-specs/blob/main/proto/voicedock/core/stt/v1/stt_api.proto)                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| proto version          | v1                                                                                                                                                                                                                                       |
| implementation example | [sttwhisper](https://github.com/voicedock/sttwhisper)                                                                                                                                                                                    |
| area of application    | <ul><li>voice assistant</li><li>recognition of voice messages in instant messengers</li><li>Next gen interactive voice response (IVR)</li><li>Next gen voice answering machine</li><li>smart voice recorder</li><li>and others</li></ul> |

## TTS API
The API gets the text, language, speaker name and synthesizes the voice audio stream in
PCM format (little-endian 16-bit bytes).

| proto                  | [tts_api.proto](https://github.com/voicedock/voicedock-specs/blob/main/proto/voicedock/core/tts/v1/tts_api.proto)                               |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------|
| proto version          | v1                                                                                                                                              |
| implementation example | [ttspiper](https://github.com/voicedock/ttspiper)                                                                                               |
| area of application    | <ul><li>voice assistant</li><li>Next gen interactive voice response (IVR)</li><li>Next gen voice answering machine</li><li>and others</li></ul> |

## AI Chat API
The API accepts text and returns a stream of generated text tokens.

| proto                  | [aichat_api.proto](https://github.com/voicedock/voicedock-specs/blob/main/proto/voicedock/core/aichat/v1/aichat_api.proto)                                                   |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| proto version          | v1                                                                                                                                                                           |
| implementation example | [aichatllama](https://github.com/voicedock/aichatllama)                                                                                                                      |
| area of application    | <ul><li>voice assistant</li><li>Next gen interactive voice response (IVR)</li><li>Next gen voice answering machine</li><li>Text summary service</li><li>and others</li></ul> |


