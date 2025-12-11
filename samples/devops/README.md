# DevOps & Architecture

Samples demonstrating infrastructure and design patterns.

---

## Daemon Architecture with IPC

From **StreamAudio** - background process with hot model loading:

```python
class TTSDaemon:
    """Background TTS service with IPC communication"""
    
    def __init__(self):
        self.voice = Voice(headless=True)
        self.listener = Listener(('localhost', 5050), authkey=b'secret')
    
    def run(self):
        while True:
            conn = self.listener.accept()
            command = conn.recv()
            
            if command['action'] == 'say':
                audio = self.voice.say(command['text'])
                conn.send({'audio': audio})
            elif command['action'] == 'reload_model':
                self.voice = Voice(model_path=command['model'])
            
            conn.close()
```

[View StreamAudio demo](../../projects/StreamAudio/)

---

## Plugin Auto-UI Generation

From **DNetCon** - dynamic interface from plugin definitions:

```python
PLUGIN_SCHEMA = {
    'name': 'Image Processor',
    'params': [
        {'name': 'input_dir', 'type': 'path', 'required': True},
        {'name': 'quality', 'type': 'slider', 'min': 1, 'max': 100},
        {'name': 'format', 'type': 'select', 'options': ['png', 'jpg', 'webp']}
    ]
}

def generate_ui(schema):
    """Build web form from plugin schema"""
    html = f"<h3>{schema['name']}</h3><form>"
    for param in schema['params']:
        html += render_input(param)
    html += "</form>"
    return html
```

[View DNetCon demo](../../projects/DNetCon/)

---

## Multi-Service Pipeline Orchestration

From **POD Pipeline** - coordinating ComfyUI and Printify:

```python
def run(self):
    """Execute complete POD workflow"""
    # Validate all services are accessible
    self.validate_configuration()
    
    # Process images through ComfyUI
    images = self.get_input_images()
    processed = self.process_images(images)  # ComfyUI
    
    # Deploy to Printify
    products = self.upload_to_printify(processed)
    
    # Report and cleanup
    self.print_summary()
    self.cleanup_processed_images()
```

[View POD Pipeline demo](../../projects/POD/)
