# AI-Powered Workflows

Samples demonstrating AI integration patterns.

---

## LLM Integration with Mode-Specific Processing

From **DNetAether** - routing transcribed speech through different LLM pipelines based on user mode:

```python
def _process_with_llm(self, text: str, mode: str):
    if mode == 'flow':
        # Refine text for clarity and grammar
        prompt = f"Improve this text for clarity: {text}"
    elif mode == 'code':
        # Generate code from natural language
        prompt = f"Generate Python code for: {text}"
    elif mode == 'assistant':
        # Conversational response
        prompt = f"Respond helpfully to: {text}"
    
    response = self.llm.generate(prompt)
    return response
```

[View DNetAether demo](../../projects/DNetAether/)

---

## Local Speech Recognition (Whisper)

From **DNetAether** - offline transcription with audio capture:

```python
def _process_audio_final(self, mode: str):
    audio_data = np.concatenate(self.audio_buffer)
    audio_float = audio_data.astype(np.float32) / 32768.0
    
    # Local Whisper - no cloud dependency
    result = self.whisper_model.transcribe(audio_float)
    transcribed_text = result['text'].strip()
    
    if mode in ['flow', 'code', 'assistant']:
        return self._process_with_llm(transcribed_text, mode)
    return transcribed_text
```

[View DNetAether demo](../../projects/DNetAether/)

---

## Autonomous Cognitive Loop

From **Choir** - AI that thinks without prompts:

```python
def _loop(self):
    while self.running:
        # 1. Perceive (External Input)
        try:
            inp = self.input_queue.get(timeout=0.1) 
            self._process_input(inp)
            continue
        except queue.Empty:
            pass

        # 2. Deliberate (Internal Thought Queue)
        if not self.thought_queue.empty():
            self._process_internal_thought(thought_task)
            continue
        
        # 3. Idle / Daydream
        self._idle_process()
```

[View Choir demo](../../projects/Choir/)
