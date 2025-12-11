# AirControl

Gesture-based computer control via Leap Motion.

---

## Purpose & Impact

Control your computer with hand gestures. No keyboard, no mouse - just natural human motion. Define custom poses, train the system to recognize them, map them to any action.

**Value**: Hands-free computing. Accessibility. A new interaction paradigm.

---

## Philosophy

> *"Increasing human bandwidth"*

The keyboard and mouse are bottlenecks. They require visual attention, precise positioning, specific finger movements. Gestures are different - they can be performed while looking elsewhere, can be broader and more intuitive.

This is exploration into what computing looks like when the interface matches the human, not the other way around.

---

## Technical Highlights

### Leap Motion SDK Integration

Real-time hand tracking with pose recognition:

```python
def gesture_recognition_loop():
    while controller.is_connected:
        frame = controller.frame()
        
        for hand in frame.hands:
            # Extract hand pose data
            pose = extract_pose(hand)
            
            # Match against trained gestures
            gesture = recognize_gesture(pose)
            
            if gesture:
                execute_action(gesture.action)
```

### Custom Pose Training

Web interface for teaching the system new poses:

```python
class PoseTrainer:
    def record_pose(self, name: str, samples: int = 30):
        """Record samples of a pose for training"""
        for i in range(samples):
            pose_data.append(current_hand_pose())
        
        # Train classifier on collected samples
        self.classifier.fit(name, pose_data)
```

---

## Challenges Overcome

**Problem**: Gesture recognition accuracy with limited hardware precision. The Leap Motion sensor has noise and tracking gaps.

**Solution**: Statistical pose matching with tolerance thresholds. Collect multiple samples per gesture, match against average with configurable confidence requirements.

---

## Technologies

Python | Leap Motion SDK | Gesture recognition | Flask web UI

---

## Media

- [ ] **GIF**: Hand gesture triggering desktop action
- [ ] **Screenshot**: Pose training interface in browser
