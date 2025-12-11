# StreamAudio

Text-to-speech library with natural prosody and voice conversion.

---

## Purpose & Impact

AI assistants speak to us constantly now. Most sound robotic - flat, monotone, unpleasant to listen to for extended periods. StreamAudio generates speech with natural rhythm, pitch variation, and optional voice conversion to sound genuinely human.

**Value**: If AI is going to be part of our daily workflow, it should sound like a voice we want to hear.

---

## Philosophy

**With accessibility comes understanding.**

Voice is intimate. When software speaks, it enters a deeply human space. This project treats that seriously - not just generating audio, but crafting speech that respects the listener's experience.

The technical challenge of natural prosody became an exploration of what makes human speech feel alive: subtle pitch wandering, breath pauses, dynamic pacing. Then implementing those patterns computationally.

---

## Technical Highlights

### Perlin Noise Dynamics

Human speech doesn't follow patterns - it wanders. Perlin noise provides organic variation:

```python
def process(self, text):
    for sentence in sentences:
        self.noise_pos += self.settings['noise_step']
        pitch_val = self._map_noise_to_range(
            self.pitch_noise(self.noise_pos), 
            self.settings['pitch_range'], 
            self.settings['pitch_deviation']
        )
        scale_val = self._map_noise_to_range(
            self.scale_noise(self.noise_pos), 
            self.settings['scale_range'], 
            self.settings['scale_deviation']
        )
        temp_sentence = f"[scale={scale_val:.2f}][pitch={pitch_val:.2f}]{sentence}"
```

Each sentence gets unique but coherent prosody - no two readings sound identical.

### RVC Voice Conversion

Piper TTS provides the base voice; RVC (Retrieval-based Voice Conversion) transforms it into any trained voice while preserving the dynamic prosody:

```python
# Fast-path with RVC: Bypass dynamics for minimal latency
# Piper synthesis → RVC conversion → Audio output
```

---

## Challenges Overcome

**Problem**: Real-time latency. Each processing step (synthesis, dynamics, conversion) adds delay. Users expect immediate response.

**Solution**: Chunked streaming with background RVC initialization. First audio chunk plays while processing continues. Latency feels minimal even with heavy processing.

---

## Technologies

Python | Piper TTS | RVC ONNX | Perlin noise | Audio streaming

---

## Media

- [ ] **Audio comparison**: Flat TTS vs StreamAudio dynamic prosody (waveform visualization or audio files)
- [ ] **Screenshot**: Settings showing dynamics parameters
