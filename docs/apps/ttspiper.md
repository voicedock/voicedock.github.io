# TTS Piper
Piper based VoiceDock TTS implementation.
Provides gRPC API for high quality text-to-speech (raw PCM stream) based on Piper project. Provides download of new languages and voices via API.

## Features
* Browse and download language and voice
* Text to speech conversion for 27+ languages ([see samples](https://rhasspy.github.io/piper-samples/))
* Fast performance on cpu

## Installation
Create directories for model data and configuration:
``` bash
mkdir dataset
mkdir config
```
Create a `config/ttspiper.json` configuration file or download an example configuration:
``` bash
curl -o config/ttspiper.json https://raw.githubusercontent.com/voicedock/ttspiper/main/config/ttspiper.json
```
Start in Docker:
``` bash
docker run --rm \
  -v "$(pwd)/config:/data/config" \
  -v "$(pwd)/dataset:/data/dataset" \
  -p 9997:9999 \
  ghcr.io/voicedock/ttspiper:latest ttspiper
```

## Configuration
[See on Github](https://github.com/voicedock/ttspiper).

## Languages support
* Català (Catalan, Spain)
* Dansk (Danish, Denmark)
* Deutsch (German, Germany)
* Ελληνικά (Greek, Greece)
* English (English, Great Britain)
* English (English, United States)
* Español (Spanish, Spain)
* Español (Spanish, Mexico)
* Suomi (Finnish, Finland)
* Français (French, France)
* íslenska (Icelandic, Iceland)
* Italiano (Italian, Italy)
* ქართული ენა (Georgian, Georgia)
* қазақша (Kazakh, Kazakhstan)
* नेपाली (Nepali, Nepal)
* Nederlands (Dutch, Belgium)
* Nederlands (Dutch, Netherlands)
* Norsk (Norwegian, Norway)
* Polski (Polish, Poland)
* Português (Portuguese, Brazil)
* Русский (Russian, Russia)
* Svenska (Swedish, Sweden)
* Kiswahili (Swahili, Democratic Republic of the Congo)
* украї́нська мо́ва (Ukrainian, Ukraine)
* Tiếng Việt (Vietnamese, Vietnam)
* 简体中文 (Chinese, China)
