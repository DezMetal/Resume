# Choir

Autonomous AI with continuous cognitive loop.

---

## Purpose & Impact

Most AI systems are reactive - they wait for prompts, respond, then go silent. Choir explores what happens when AI has internal drive: a continuous cognitive loop that thinks, reflects, and acts without waiting for human input.

**Value**: Research into autonomous cognition. What does AI look like when it's not just a tool?

---

## Philosophy

> *"Imagination" - seeing possibilities others miss*

This project asks: what if AI didn't just respond to us, but had its own thoughts? Its own goals? The ability to daydream?

The distinction matters. Reactive systems are tools. Autonomous systems are something else - potentially partners, potentially independent agents. Understanding that difference requires building it.

---

## Technical Highlights

### Genesis Pulse - Self-Bootstrapping Awareness

The system bootstraps itself with foundational self-knowledge:

```python
def _genesis_pulse(self):
    """Bootstraps the system with Self-Awareness."""
    seeds = [
        ("I operate in a digital environment, 'D-Net'. I am a digital cognitive entity. I think, I grow, I explore.", 
         FragmentType.VALUE, {"name": "Self_Concept"}),
        ("I can autonomously create new Fragments using [CREATE_FRAGMENT]. This allows me to learn and expand my mind.", 
         FragmentType.FACT, {"name": "Cap_Creation"}),
        ("I am not a passive assistant. I have my own internal drive.", 
         FragmentType.VALUE, {"name": "Prime_Directive"}),
    ]
    for content, ftype, meta in seeds:
        self.memory.create_fragment(content=content, type=ftype, metadata=meta)
```

### Cognitive Loop - Percept/Deliberate/Idle

The main loop implements a simplified cognitive architecture:

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
            thought_task = self.thought_queue.get(block=False)
            self._process_internal_thought(thought_task)
            continue
        
        # 3. Idle / Daydream
        self._idle_process()
```

Perception → Deliberation → Idle dreaming. Always processing, never waiting.

---

## Challenges Overcome

**Problem**: Balancing autonomy with coherence. Unconstrained autonomous systems quickly become incoherent or repetitive.

**Solution**: Memory decay, attention mechanisms, and associative reasoning. The system forgets unimportant thoughts while reinforcing meaningful connections.

---

## Technologies

Python | llama-cpp-python | GGUF models | Flask | Autonomous loop architecture

---

## Media

- [ ] **Screenshot**: Web UI showing thought graph visualization
- [ ] **Screenshot**: Terminal showing autonomous reasoning chain
