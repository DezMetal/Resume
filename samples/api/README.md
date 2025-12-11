# API Development

Samples demonstrating API design patterns.

---

## Dual Authentication Decorator

From **D-Net Platform** - unified auth for both web sessions and API keys:

```python
def api_auth_required(f):
    """
    Supports BOTH internal frontend calls (session-based) 
    AND external API calls (API key).
    """
    @wraps(f)
    def decorated_function(*args, **kwargs):
        # Try session auth first (frontend)
        if current_user.is_authenticated:
            g.api_user = current_user
            return f(*args, **kwargs)
        
        # Fall back to API key (external)
        api_key = request.headers.get('X-API-Key')
        if api_key:
            user = User.query.filter_by(api_key=api_key).first()
            if user:
                g.api_user = user
                return f(*args, **kwargs)
        
        return jsonify({'error': 'Authentication required'}), 401
    return decorated_function
```

[View D-Net Platform demo](../../projects/DNet/)

---

## File-Based IPC Protocol

From **DNetCon** - inter-process messaging for workflow orchestration:

```python
def send_command(target: str, action: str, data: dict):
    """Write command to IPC file for external programs to consume"""
    ipc_file = f"ipc/{target}_inbox.json"
    with open(ipc_file, 'w') as f:
        json.dump({
            'action': action, 
            'data': data, 
            'timestamp': time.time()
        }, f)

def on_file_change(event):
    """Watchdog monitors for changes and triggers processing"""
    if event.src_path.endswith('_inbox.json'):
        process_command(event.src_path)
```

[View DNetCon demo](../../projects/DNetCon/)

---

## REST Endpoint Pattern

From **DNetAva** - avatar control API:

```python
@app.route('/api/speak', methods=['POST'])
@jwt_required
def speak():
    data = request.json
    text = data.get('text')
    
    # Generate speech with viseme data
    audio, visemes = voice.say(text, return_visemes=True)
    
    return jsonify({
        'audio': encode_audio(audio),
        'visemes': visemes,
        'duration': len(audio) / sample_rate
    })
```

[View DNetAva demo](../../projects/DNetAva/)
