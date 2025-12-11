# DNet Platform

Full-stack AI platform with personas, content management, and e-commerce.

---

## Purpose & Impact

The infrastructure for AI-powered services. DNet provides persona creation, conversation management, content cards, and Stripe integration - a complete platform for building and monetizing AI experiences.

**Value**: Not just a project, but a platform. The foundation for multiple applications.

---

## Philosophy

> *"Discretion" - sound technical decisions made independently*

Building a platform requires making architectural choices that compound over time. Database design, authentication strategy, API structure - each decision shapes what's possible later.

This project demonstrates the ability to make those decisions well: choosing Flask blueprints for modularity, implementing dual authentication for flexibility, designing schemas that scale.

---

## Technical Highlights

### Dual Authentication Decorator

One decorator handles both web sessions and API keys:

```python
def api_auth_required(f):
    """
    UNIFIED API AUTHENTICATION DECORATOR
    
    Supports BOTH internal frontend calls (session-based) 
    AND external API calls (API key).
    
    Usage:
        @api.route('/services')
        @api_auth_required
        def AgentServices():
            user = g.api_user  # Works for both auth types
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

### Persona System

AI personas with dynamic BIO templates that shape their behavior:

```python
BIO_TEMPLATE = """
You are {persona_name}.
{persona_description}

Your personality traits: {traits}
Your speaking style: {style}
"""
```

---

## Challenges Overcome

**Problem**: Authentication that works for both browser sessions (cookies) and API consumers (keys) without duplicating logic.

**Solution**: Single decorator that checks session first, falls back to API key, and populates `g.api_user` consistently for downstream code.

---

## Technologies

Python | Flask | SQLAlchemy | Stripe | Gemini API | JWT | Docker

---

## Media

- [ ] **Screenshot**: Dashboard showing personas and content cards
- [ ] **Screenshot**: API response example in Postman/curl
- [ ] **Screenshot**: Admin panel with platform settings
