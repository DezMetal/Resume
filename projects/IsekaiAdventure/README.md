# IsekaiAdventure

AI language learning through immersive narrative.

---

## Purpose & Impact

Born from the language learning plateau. You've outgrown beginner resources but aren't ready for native content. This fills the gap: an AI-driven narrative that adapts to your level and teaches through immersion.

**Value**: Language learning that doesn't feel like studying.

---

## Philosophy

**With accessibility comes understanding and inspiration.**

Traditional language learning hits a wall. Textbooks are finite. Beginner communities become too easy. Native content is frustrating. The middle ground barely exists.

This project creates that middle ground. An AI that knows your level: challenges without overwhelming, teaches without lecturing. Story creates stakes; stakes create engagement; engagement creates learning.

---

## Technical Highlights

### Context Window Management

Long-form coherent storytelling requires careful context management:

```python
class StoryEngine:
    def __init__(self, target_language: str):
        self.context_window = []
        self.story_state = {}
        self.vocabulary_level = 0.5  # 0-1 scale
    
    def generate_next(self, player_input: str):
        # Build prompt with story context
        prompt = self._build_contextual_prompt(
            history=self.context_window[-10:],  # Recent exchanges
            state=self.story_state,              # World state
            level=self.vocabulary_level,         # Language complexity
            input=player_input
        )
        
        # Generate response with language integration
        return self.llm.generate(prompt)
```

### Adaptive Language Integration

Japanese woven naturally into English narrative, calibrated to level:

```python
def integrate_language(self, text: str, level: float):
    """
    At low levels: occasional words with context clues
    At mid levels: full phrases with natural translation
    At high levels: extended passages, minimal scaffolding
    """
```

---

## Challenges Overcome

**Problem**: Maintaining story coherence across many exchanges. LLMs forget context and contradict earlier narrative.

**Solution**: Explicit story state tracking. Key facts, character relationships, and plot points stored separately and injected into each prompt.

---

## Technologies

Python | Gemini API | Context management | Interactive fiction

---

## Media

- [ ] **Screenshot**: Story interface showing Japanese integrated in English narrative
- [ ] **Screenshot**: Vocabulary appearing naturally in context
