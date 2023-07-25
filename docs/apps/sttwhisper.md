# STT Whisper
Whisper.cpp based VoiceDock STT implementation.
Provides gRPC API for high quality speech-to-text (from raw PCM stream) based on Whisper.cpp project. Provides download of new language packs via API.

## Features
* Browse and download language packs (models in ggml format)
* Speech to text conversion for 99+ languages
* Automatic language recognition
* GPU support

## Installation
Create directories for model data and configuration:
``` bash
mkdir dataset
mkdir config
```
Create a `config/sttwhisper.json` configuration file or download an example configuration:
``` bash
curl -o config/sttwhisper.json https://raw.githubusercontent.com/voicedock/sttwhisper/main/config/sttwhisper.json
```

=== "Docker (on CPU)"

    ``` bash
    docker run --rm \
        -v "$(pwd)/config:/data/config" \
        -v "$(pwd)/dataset:/data/dataset" \
        -p 9999:9999 \
        ghcr.io/voicedock/sttwhisper:latest sttwhisper
    ```

=== "Docker (on GPU)"

    ``` c++
    docker run --rm \
        -v "$(pwd)/config:/data/config" \
        -v "$(pwd)/dataset:/data/dataset" \
        -p 9999:9999 \
        ghcr.io/voicedock/sttwhisper:gpu sttwhisper
    ```

## Configuration
[See on Github](https://github.com/voicedock/sttwhisper).

## Languages support
en, zh, de, es, ru, ko, fr, ja, pt, tr, pl, ca, nl, ar, sv, it, id, hi, fi, vi, iw, uk, el, ms, cs, ro, da, hu, ta, no,
th, ur, hr, bg, lt, la, mi, ml, cy, sk, te, fa, lv, bn, sr, az, sl, kn, et, mk, br, eu, is, hy, ne, mn, bs, kk, sq, sw,
gl, mr, pa, si, km, sn, yo, so, af, oc, ka, be, tg, sd, gu, am, yi, lo, uz, fo, ht, ps, tk, nn, mt, sa, lb, my, bo, tl,
mg, as, tt, haw, ln, ha, ba, jw.