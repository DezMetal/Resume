# DNetAva

Interactive 3D avatar frontend with voice integration.

---

## Purpose & Impact

Giving AI a face. A presence. Something to look at when it speaks. DNetAva renders a 3D avatar in browser that synchronizes with StreamAudio TTS, ready to receive API commands and express personality.

**Value**: The foundation for embodied AI interaction.

---

## Philosophy

> *"From mind to matter"*

This project exemplifies the D-Net Lab ethos: conceived one night, realized the next day.

The spark was simple - what if AI could look at you while it talked? Within 24 hours, there was a working avatar in browser, using StreamAudio for voice, synchronized with lip animations, ready for API integration.

That's the skill being demonstrated: the ability to take an idea from imagination to functional prototype rapidly. Not perfection - foundation. Something that works, something to build on.

---

## Technical Highlights

### Avatar Speech Synchronization

StreamAudio TTS integration with real-time viseme mapping:

```javascript
async function handleSpeak(data) {
    // Receive speech data from API
    const { audio, visemes, duration } = data;
    
    // Play audio
    playAudio(audio);
    
    // Animate visemes synchronized to speech
    animateVisemes(visemes, duration);
}
```

### Cross-Model Compatibility

Designed to work with different avatar models through standardized morph target detection:

```javascript
function detectMorphTargets(model) {
    // Scan model for available blend shapes
    // Map standard viseme names to model-specific targets
    // Fall back to "puppet mode" if no morphs available
}
```

---

## Challenges Overcome

**Problem**: Different avatar models use different naming conventions for blend shapes. A solution that works for one model breaks on another.

**Solution**: Flexible morph target detection with fallback systems. If the expected blend shapes aren't available, the avatar uses alternative animation methods (jaw rotation, head scaling).

---

## Technologies

Three.js | WebGL | StreamAudio | Flask API | GLTF/GLB models

---

## Media

- [ ] **GIF**: Avatar speaking with lip sync and expressions
- [ ] **Screenshot**: Avatar in browser with configuration panel
- [ ] **Screenshot**: Different avatar models working with same system
