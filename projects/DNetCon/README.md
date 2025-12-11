# DNetCon

Workflow orchestration for chaining programs together.

---

## Purpose & Impact

Any program that can read a file can participate in an automated workflow. DNetCon provides the glue: file-based IPC, trigger systems (schedule, file-watch, voice), and auto-generated UIs for each plugin.

**Value**: Universal automation without learning each tool's specific API.

---

## Philosophy

> *"With accessibility comes understanding"*

Complex automation shouldn't require programming expertise. If someone can describe what they want - "when this file changes, run that script" - they should be able to build it.

This tool lowers the barrier. Plugins describe their capabilities; the UI generates itself. Workflows connect visually. The complexity is hidden; the power is accessible.

---

## Technical Highlights

### File-Based IPC Protocol

Universal communication that works with any program:

```python
# Write command to IPC file
def send_command(target: str, action: str, data: dict):
    ipc_file = f"ipc/{target}_inbox.json"
    with open(ipc_file, 'w') as f:
        json.dump({'action': action, 'data': data, 'timestamp': time.time()}, f)

# Watchdog monitors for changes
def on_file_change(event):
    if event.src_path.endswith('_inbox.json'):
        process_command(event.src_path)
```

### Plugin Auto-UI Generation

Plugins declare their parameters; the web interface builds itself:

```python
PLUGIN_SCHEMA = {
    'name': 'Image Processor',
    'params': [
        {'name': 'input_dir', 'type': 'path', 'required': True},
        {'name': 'quality', 'type': 'slider', 'min': 1, 'max': 100}
    ]
}
# UI generates input fields from schema automatically
```

---

## Challenges Overcome

**Problem**: Making complex workflows accessible without dumbing them down. Users need power and simplicity.

**Solution**: Visual workflow editor with drag-and-drop connections. Advanced options available but hidden by default.

---

## Technologies

Python | Flask | Watchdog | File IPC | Plugin architecture

---

## Media

- [ ] **Screenshot**: Workflow editor with connected nodes
- [ ] **Screenshot**: Auto-generated plugin configuration UI
