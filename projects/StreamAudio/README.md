# StreamAudio

Neural TTS module with dynamic processing and RVC voice conversion.

## Overview
A reusable TTS engine that produces natural-sounding speech through Perlin noise-based pitch and speed variation. Includes RVC voice conversion layer and daemon architecture for hot model loading. Used as a git submodule across multiple D-Net projects.

## Key Features
- **Piper TTS** - fast neural text-to-speech
- **Perlin noise dynamics** - organic pitch/speed variation per sentence
- **RVC voice conversion** - transform voice characteristics
- **Daemon architecture** - keep model hot for instant responses
- **File tags** - control output via inline tags ([save=path], [bytes], etc.)

## Technologies
- Python | Piper TTS | RVC | Perlin noise | IPC daemon | Audio processing

## Media
*Add to `/media` folder*
- [ ] Audio sample: before/after dynamic processing
- [ ] Screenshot: configuration options
