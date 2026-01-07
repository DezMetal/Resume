# Envoy

AI-powered interviewer agent for natural data collection.

---

## Purpose & Impact

Surveys and forms get poor response rates and shallow data. Envoy replaces static questionnaires with adaptive, conversational interviews that feel natural to users while systematically extracting the data you need.

**Value**: Better data through better conversations. Users engage more, reveal more, and complete more.

---

## Philosophy

**Data collection should feel like conversation.**

Traditional forms ask the same questions in the same order regardless of context. A skilled human interviewer adapts - following up on interesting responses, skipping irrelevant sections, probing deeper when needed.

Envoy brings that adaptability to automated data collection. The AI understands what information is needed and navigates toward it naturally, making the experience feel less like a form and more like a helpful discussion.

---

## Technical Highlights

### Mission-Based Interview Structure

Interviews are defined by "missions" - structured specifications of what data needs to be collected:

```python
mission = {
    "objective": "Gather user feedback on service experience",
    "required_fields": [
        {"name": "satisfaction_score", "type": "scale", "range": "1-10"},
        {"name": "pain_points", "type": "text", "description": "specific frustrations"},
        {"name": "recommendations", "type": "text", "optional": True}
    ],
    "tone": "professional but friendly",
    "max_turns": 15
}
```

### Conversational Data Extraction

Natural language processing identifies when target data has been collected:

```python
def _extract_field_from_response(self, response: str, field: dict):
    # Use LLM to identify if response contains target data
    # Validate against field type and constraints
    # Return structured data or None if not found
    
    extraction_prompt = f"""
    Extract '{field['name']}' from this response: {response}
    Expected type: {field['type']}
    Return JSON or 'NOT_FOUND'
    """
    return self.llm.extract(extraction_prompt)
```

### End-of-Task Detection

Intelligent detection of when interviews should conclude:

```python
def _check_completion(self):
    # All required fields collected?
    # Max turns reached?
    # User signaling end of conversation?
    # Natural conclusion point detected?
    
    if all(f['collected'] for f in self.required_fields):
        return self._generate_report()
```

---

## Challenges Overcome

**Problem**: Users give vague or incomplete answers that don't satisfy data requirements.

**Solution**: Follow-up question generation that probes for specifics without feeling pushy. The AI tracks what's been collected and what's still needed, naturally steering conversation toward gaps.

---

## Technologies

Python | Flask | Gemini API | Structured Output | Session Management | Report Generation

---

## Media

- [ ] **Screenshot**: Interview in progress showing natural conversation flow
- [ ] **Screenshot**: Generated report with extracted data fields
- [ ] **GIF**: Real-time data extraction visualization
