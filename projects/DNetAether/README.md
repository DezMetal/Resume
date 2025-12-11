# DNetAether

Voice productivity tool for increased human bandwidth.

---

## Purpose & Impact

Your hands are on the keyboard. Your attention is on code. But you need to capture a thought, send a message, or generate a snippet. DNetAether bridges that gap - voice commands that integrate seamlessly into any workflow.

**Value**: Hands stay on keys. Attention stays on work. Voice handles the rest.

---

## Philosophy

**Increasing human bandwidth.**

Every context switch costs focus. Every trip to the mouse, every alt-tab, every manual copy-paste - they accumulate into fragmented attention. This tool exists to eliminate those micro-interruptions.

The goal isn't replacing typing. It's augmenting it. Dictation for prose, code generation for boilerplate, quick commands for system control - each mode optimized for its purpose.

---

## Technical Highlights

### Multi-Mode Hotkey State Machine

Seven distinct modes, each with dedicated hotkeys and behaviors:

```python
self.hotkeys: Dict[str, Set[str]] = {
    'command': parse(self.config.get('command_hotkey', 'ctrl_r')),
    'typing': parse(self.config.get('typing_hotkey', 'ctrl_l+shift_l')),
    'code': parse(self.config.get('code_hotkey', 'alt_l+shift_l')),
    'flow': parse(self.config.get('flow_hotkey', 'alt_l+f')),
    'assistant': parse(self.config.get('assistant_hotkey', 'alt_l+x')),
    'chat': parse(self.config.get('chat_hotkey', 'ctrl_l+alt_l')),
    'click_reader': parse(self.config.get('click_reader_hotkey', 'shift_r+alt_r'))
}
```

- **Typing**: Raw transcription → clipboard
- **Flow**: Transcription → LLM refinement → clipboard
- **Code**: Natural language → generated code
- **Command**: Voice-triggered system actions
- **Assistant**: Conversational AI with voice feedback
- **ClickReader**: Read screen content aloud on click

### Whisper + LLM Pipeline

Local Whisper model for offline transcription, piped to Gemini for intelligent processing:

```python
def _process_with_llm(self, text: str, mode: str):
    # Whisper transcription complete
    # Route to appropriate LLM processing based on mode
    # Apply volume ducking during TTS response
```

---

## Challenges Overcome

**Problem**: Hotkey conflicts when GUI windows have focus. Different applications intercept keys differently.

**Solution**: Global hotkey listener running in dedicated thread with careful state management. Hotkeys work regardless of active application.

---

## Technologies

Python | Whisper | Gemini API | Piper TTS | pynput | Volume ducking | StreamAudio

---

## Media

- [ ] **GIF**: Voice dictation flowing into text editor in real-time
- [ ] **GIF**: Code generation mode - speaking requirement, receiving code
- [ ] **Screenshot**: Settings/configuration interface
