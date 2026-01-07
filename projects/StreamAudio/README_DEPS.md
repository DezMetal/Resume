# StreamAudio Dependencies Installation

StreamAudio requires additional dependencies that are NOT in requirements.txt:

```bash
pip install piper-tts
pip install audiotsm
pip install perlin-noise
pip install rich
pip install scipy
```

**OR** just disable TTS if not needed - the app works fine without it.

To add these to your venv:
```bash
.\venv\Scripts\activate
pip install piper-tts audiotsm perlin-noise rich scipy
```

The warning "StreamAudio library not found" means one of these is missing.
