# VirtualLense

Screen region analysis with automation potential.

---

## Purpose & Impact

See the screen. Understand it. Act on it. VirtualLense captures regions, extracts text via OCR, and pipes output to files for integration with other systems. It can also control mouse input.

**Value**: The eyes and hands of automation. Foundation for visual workflows.

---

## Philosophy

**From mind to matter.**

The potential here is significant: any visual information on screen becomes accessible to automation. Status indicators, text displays, game state, application output - all can be read, interpreted, and acted upon.

This isn't just an OCR tool. It's visual perception for automated systems.

---

## Technical Highlights

### Screen Capture + OCR Pipeline

Region selection through processing to output:

```python
def capture_and_process(region: Rect):
    # Capture screen region
    screenshot = capture_region(region)
    
    # OCR extraction
    text = ocr_engine.read(screenshot)
    
    # Output to IPC file for external programs
    with open('ipc/virtuallense_output.txt', 'w') as f:
        f.write(text)
    
    return text
```

### IPC Integration

Output writes to files that other programs can monitor:

```python
# Other programs watch for changes
# DNetCon can trigger workflows based on extracted text
# Automation chains become possible
```

### Input Control

Beyond reading - can control mouse position and clicks:

```python
def click_at(x, y):
    # Move to coordinates
    # Trigger click
    # Enable fully automated visual workflows
```

---

## Challenges Overcome

**Problem**: Real-time processing without impacting system performance. Screen capture and OCR are resource-intensive.

**Solution**: Targeted region capture (not full screen), optimized OCR settings, and configurable update intervals.

---

## Technologies

Python | EasyOCR | OpenCV | Tkinter | Screen capture | Mouse control

---

## Media

- [ ] **GIF**: Region selection → text extraction appearing in output
- [ ] **GIF**: IPC trigger activating another program based on screen content
