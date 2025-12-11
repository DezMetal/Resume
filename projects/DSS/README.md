# DSS - D-Net Signature Stylesheet

Custom CSS framework with geometric aesthetics and theming.

---

## Purpose & Impact

Consistent visual identity across all D-Net projects. Geometric cuts, glow effects, light/dark theming - a signature look that's instantly recognizable.

**Value**: Design system that enables rapid development with guaranteed quality.

---

## Philosophy

> *"Discretion" - sound decisions made independently*

Every D-Net project shares visual DNA. Not through copy-paste, but through a systematic design language. CSS variables define the vocabulary; components implement the grammar.

This is invisible infrastructure. Users don't see the stylesheet; they see cohesive products. But the stylesheet is why those products feel connected.

---

## Technical Highlights

### CSS Variable Architecture

Theme switching through variable redefinition:

```css
:root {
  /* Dark theme (default) */
  --dss-color-background-primary: #0D1117;
  --dss-color-text-primary: #c9d1d9;
  --dss-color-accent-glow: #00e0ff;
}

.dss-theme-light {
  /* Light theme override */
  --dss-color-background-primary: #f0f2f5;
  --dss-color-text-primary: #22272e;
}
```

### Geometric Clip-Path System

Signature cut corners as reusable patterns:

```css
.dss-card {
  clip-path: polygon(
    var(--dss-cut-size) 0,      /* Top-left cut */
    100% 0,                      /* Top-right */
    100% calc(100% - var(--dss-cut-size)),  /* Bottom-right cut */
    calc(100% - var(--dss-cut-size)) 100%,
    0 100%,
    0 var(--dss-cut-size)
  );
}
```

### Background Texture Patterns

Subtle grid and dot patterns for visual depth:

```css
.dss-bg-grid {
  --grid-size: 2.506rem;
  background-image:
    linear-gradient(to right, var(--dss-bg-texture-color) 1px, transparent 1px),
    linear-gradient(to bottom, var(--dss-bg-texture-color) 1px, transparent 1px);
  background-size: var(--grid-size) var(--grid-size);
}
```

---

## Challenges Overcome

**Problem**: Maintaining design consistency across projects with different requirements.

**Solution**: Modular system. Core variables and geometry are universal; component styles can be extended per-project.

---

## Technologies

CSS | CSS variables | Geometric design | Theme system

---

## Media

- [ ] **Screenshot**: Side-by-side light/dark theme comparison
- [ ] **Screenshot**: Component gallery showing cards, buttons, forms
