# Media Capture Guide for Portfolio Projects

**Purpose:** This guide provides specific, step-by-step instructions for capturing screenshots and recordings of each project to showcase in your portfolio, resume, and job applications.

**Tools Needed:**
- **Windows Snipping Tool** (Win + Shift + S) - For quick screenshots
- **OBS Studio** (free) or **ShareX** (free) - For screen recordings
- **Image editor** (Paint, Paint.NET, or GIMP) - For annotations/cropping

**General Guidelines:**
- Save all media to: `Resume/Projects/[ProjectName]/SCREENSHOTS/`
- **Format**: PNG for screenshots, MP4 for videos
- **Resolution**: 1920x1080 preferred (full HD)
- **Naming**: Descriptive names like `dnet_ai_chat_interface.png`
- **Clean**: Close unnecessary browser tabs, hide personal info

---

## Project 1: D-Net Platform (10 items)

**Setup:**
1. Start the D-Net application locally
2. Clear browser cache/cookies for fresh session
3. Use demo/test account (not personal data)
4. Optional: Enable Stripe test mode for payment flows

### Screenshots to Capture:

**1. Homepage - Logged Out View** (`dnet_homepage_logged_out.png`)
- URL: Your D-Net homepage
- Show: Hero section, value proposition, CTA buttons
- Ensure: Professional, polished landing page

**2. Registration/Login Flow** (`dnet_auth_flow.png`)
- Capture: Registration form OR login page
- Show: Clean authentication UI
- Optional: Blur any test emails if visible

**3. User Dashboard** (`dnet_user_dashboard.png`)
- URL: Main dashboard after login
- Show: Navigation, persona cards, content overview
- Ensure: Multiple personas visible (if applicable)

**4. AI Persona Chat Interface** (`dnet_ai_chat.png`)
- Show: Active conversation with AI persona
- Include: Chat history (3-5 messages), input box, persona name/avatar
- Highlight: Message history shows contextual awareness

**5. AI Tool-Calling in Action** (`dnet_ai_tool_calling.png`)
- Capture: AI creating a page or product via chat
- Show: User request + AI response mentioning action taken
- Example: "I've created a new page titled 'About Us'..."

**6. Page Creation Modal/Interface** (`dnet_page_creation.png`)
- Show: Page builder or creation form
- Include: Title field, content editor, save button
- Optional: Show rich text editor if applicable

**7. Content Card with Embedded Product** (`dnet_content_card.png`)
- Show: A content card displaying a product
- Include: Product image, title, description, price/CTA
- Highlight: Modular card architecture

**8. Theme Customizer/DSS in Action** (`dnet_theme_customizer.png`)
- Show: Theme settings panel OR before/after theme toggle
- Include: Color scheme options, geometry settings
- Demonstrate: Your custom DSS design system

**9. Admin Panel - Subscription Settings** (`dnet_admin_subscriptions.png`)
- URL: Admin or settings page
- Show: Subscription tier management (Echo/Pulse/Nexus)
- Include: Usage tracking, tier limits
- **Blur/redact**: Any real payment info

**10. Stripe Checkout Flow** (`dnet_stripe_checkout.png`)
- Use: **Test mode** only (use Stripe test card 4242 4242 4242 4242)
- Show: Checkout page with subscription tiers
- Include: Pricing, features, payment form
- **Ensure**: "TEST MODE" visible or mention in caption

**Bonus (Optional):**
- Mobile responsive views (3-4 screenshots on phone/tablet)
- API documentation page (if you have one)
- Email confirmation example (for subscriptions)

---

## Project 2: DNetCon (6 items)

**Setup:**
1. Start DNetCon locally (`python main.py`)
2. Open browser to `localhost:5000`
3. Create 1-2 demo pipelines if none exist

### Screenshots to Capture:

**1. Main Dashboard** (`dnetcon_dashboard.png`)
- Show: Pipeline list view
- Include: Multiple pipelines, enabled/disabled states, trigger types
- Highlight: Quick toggle switches

**2. Pipeline Builder Interface** (`dnetcon_pipeline_builder.png`)
- Show: Pipeline creation/edit view
- Include: Drag-and-drop area, command blocks, save button
- Demonstrate: Modular pipeline construction

**3. Program Manager Tab** (`dnetcon_program_manager.png`)
- Show: List of available programs (filesystem, datastore, aether_integration, etc.)
- Include: Program descriptions, available actions
- Highlight: Extensible plugin system

**4. Integration Tester** (`dnetcon_integration_test.png`)
- Navigate to: Programs tab > aether_integration > Test button
- Show: Test interface with status results
- Include: Buffer file paths, connection status
- Capture: Successful test result if possible

**5. Pipeline Execution - Activity Log** (`dnetcon_activity_log.png`)
- Run a test pipeline (manual trigger)
- Show: Real-time activity log
- Include: Timestamps, step outputs, success/error indicators

**6. JSON Configuration View** (Optional: `dnetcon_config_json.png`)
- Show: Example pipeline as JSON
- Include: Trigger, commands, parameters structure
- Demonstrates: Configuration-as-code approach

---

## Project 3: DNetAether (6 items)

**Setup:**
1. Run DNetAether (`python main.py`)
2. Ensure it's running in system tray
3. Open settings window
4. Prepare to demonstrate hotkeys (might need screen recording)

### Screenshots to Capture:

**1. System Tray Icon** (`dnetaether_tray_icon.png`)
- Show: DNetAether icon in Windows system tray
- Right-click to show: Context menu with options
- Include: Settings, Toggle Window, Exit options

**2. Settings Window - General Tab** (`dnetaether_settings_general.png`)
- Show: Main settings panel
- Include: Audio device selection, model configuration
- Highlight: User-friendly configuration

**3. Settings Window - Hotkeys Tab** (`dnetaether_settings_hotkeys.png`)
- Show: Hotkey configuration panel
- Include: Command hotkey, Typing hotkey, Code hotkey, Assistant hotkey
- Demonstrate: Customizable key bindings

**4. Chat Window (Overlay)** (`dnetaether_chat_window.png`)
- Trigger: Press Ctrl+Shift+Space (or configured hotkey)
- Show: Chat overlay window
- Include: Input area, settings gear icon, always-on-top indicator
- Optional: Example conversation

**5. Voice Recognition in Action** (RECORDING: `dnetaether_voice_demo.mp4` - 15 sec)
- Record: Speaking a command, text appearing
- Show: Visual feedback (press sound, release sound)
- Demonstrate: "Typing mode" or "Code mode" in action
- Duration: 10-20 seconds max

**6. ClickReader Feature** (SCREENSHOT or RECORDING: `dnetaether_clickreader.png`)
- Show: Text selected after triple-click
- Optional: Record audio output (TTS speaking the text)
- Demonstrates: Accessibility feature

---

## Project 4: VirtualLense (5 items)

**Setup:**
1. Run VirtualLense (`python main.py`)
2. Create 2-3 demo lenses on screen
3. Use Setup mode first, then Active mode

### Screenshots to Capture:

**1. Setup Mode - Lenses Visible** (`virtuallense_setup_mode.png`)
- Show: 2-3 colored overlay boxes on screen
- Include: Lenses positioned over different screen regions
- Demonstrate: Draggable/resizable functionality

**2. Controller Panel - Lens Configuration** (`virtuallense_controller_panel.png`)
- Show: Main control window
- Include: Lens list, configuration options (OCR, brightness, change detection toggles)
- Highlight: Per-lens settings

**3. Active Mode - Invisible Operation** (`virtuallense_active_mode.png`)
- Switch to: Active mode (lenses disappear)
- Show: Background application with lenses running invisibly
- Include: Controller showing active status

**4. OCR in Action - Text Detection** (`virtuallense_ocr_demo.png`)
- Point lens at: Text on screen (website, PDF, game subtitle)
- Show: Controller displaying extracted text
- Demonstrate: Real-time text extraction capability

**5. Change Detection Demo** (`virtuallense_change_detection.png`)
- Show: Controller indicating detected change in monitored region
- Include: Before/after indicator or timestamp of detected change
- Optional: Log showing change events

---

## Project 5: AirControl (4 items)

**Setup:**
1. Connect Leap Motion sensor
2. Run AirControl application
3. Open web UI (localhost:5000)

### Screenshots to Capture:

**1. Web UI - Settings Panel** (`aircontrol_settings_panel.png`)
- Show: Main settings interface
- Include: Sensitivity sliders, smoothing options, live settings editor
- Highlight: Real-time configuration capability

**2. Pose Training Interface** (`aircontrol_pose_training.png`)
- Navigate to: Pose training section
- Show: Hand pose capture, training samples list
- Include: Add/delete sample buttons, pose preview

**3. Real-Time Gesture Recognition Logs** (`aircontrol_gesture_log.png`)
- Show: Live log displaying detected gestures
- Include: Gesture names, confidence scores, timestamps
- Demonstrate: Hand tracking working in real-time

**4. Hand Tracking in Action** (RECORDING: `aircontrol_demo.mp4` - 20 sec)
- Record: Your hand over Leap Motion sensor
- Show: On-screen cursor movement or action triggered by gesture
- Include: Visual feedback from application
- Duration: 15-30 seconds showing 2-3 gestures

---

## Project 6: LangAdventure (3 items)

**Setup:**
1. Run LangAdventure (`python app.py`)
2. Create new character
3. Start game session

### Screenshots to Capture:

**1. Character Creation Screen** (`langadventure_character_creation.png`)
- Show: Character customization form
- Include: Name input, character type selection, theme options
- Highlight: Setup for language learning RPG

**2. Dual-Language Story Display** (`langadventure_dual_language.png`)
- Show: AI-generated story text in BOTH Japanese and English
- Include: Furigana above kanji characters
- Highlight: Side-by-side language display

**3. Chat Interaction with AI DM** (`langadventure_chat.png`)
- Show: Conversation thread (3-5 messages)
- Include: User input, AI Dungeon Master responses
- Demonstrate: Context-aware, educational conversation

---

## Project 7: Choir (4 items)

**Setup:**
1. Run Choir (`python app.py`)
2. Wait for cognitive loop to initialize
3. Interact with AI

### Screenshots to Capture:

**1. System Status Panel** (`choir_status_panel.png`)
- Show: Dashboard displaying Choir's status
- Include: Model loaded, context size, active/idle state
- Highlight: Local LLM operation

**2. Chat Interface** (`choir_chat_interface.png`)
- Show: Conversation with Choir AI
- Include: User messages, AI responses
- Demonstrate: Coherent, autonomous AI interactions

**3. Stream of Consciousness** (`choir_internal_thoughts.png`)
- Show: Choir's "internal monologue" or autonomous thinking
- Include: Thoughts generated while idle
- Highlight: Cognitive Entity concept

**4. Workspace Artifacts** (`choir_workspace_artifacts.png`)
- Show: Files/notes created by Choir in workspace
- Include: Filenames, creation timestamps, brief content preview
- Demonstrate: AI autonomously creating persistent artifacts

---

## Project 8: DeckGen (6 items)

**Setup:**
1. Run DeckGen (`python webapp.py`)
2. Prepare test video file (short, 30-60 sec)
3. Upload and process video

### Screenshots to Capture:

**1. Upload Interface** (`deckgen_upload_interface.png`)
- Show: File upload page
- Include: Drag-and-drop area, file type indicators, upload button
- Highlight: Clean, user-friendly interface

**2. Real-Time Processing Progress** (`deckgen_processing_progress.png`)
- Show: Progress modal/bar during transcription
- Include: Percentage complete, current step indicator (WebSocket updates visible)
- Demonstrate: Asynchronous processing with live feedback

**3. Transcription Results View** (`deckgen_transcription_results.png`)
- Show: Completed transcription with timestamps
- Include: Segment list, time codes, transcribed text
- Highlight: Intelligent chunking

**4. Translation Interface** (`deckgen_translation_interface.png`)
- Show: Translation options (Argos vs. Gemini)
- Include: Source language, target language, translate button
- Demonstrate: Dual translation provider system

**5. Export Options** (`deckgen_export_options.png`)
- Show: Export modal with format choices
- Include: JSON, CSV, Anki options
- Highlight: Multiple export formats

**6. Freemium Licensing Panel** (Optional: `deckgen_licensing.png`)
- Show: Feature unlock interface or tier comparison
- Include: Free vs. Pro features
- Demonstrate: Licensing model implementation

---

## After Capturing

### Organize Files

Create this structure:
```
Resume/
└── Projects/
    ├── DNet_Platform/
    │   └── SCREENSHOTS/
    │       ├── dnet_homepage_logged_out.png
    │       ├── dnet_ai_chat.png
    │       └── ... (all 10)
    ├── DNetCon/
    │   └── SCREENSHOTS/
    ├── DNetAether/
    │   └── SCREENSHOTS/
    └── ... (repeat for all 8 projects)
```

### Annotation (Optional but Recommended)

For key screenshots, add annotations:
- **Arrows** pointing to important features
- **Text labels** explaining what's happening
- **Highlights/circles** drawing attention to innovations

Tools:
- **ShareX** (free, built-in annotation)
- **Greenshot** (free, simple annotations)
- **Paint.NET** (free, more advanced)

### Create Screenshot Index

In each project folder, create `SCREENSHOTS/README.md`:

```markdown
# [Project Name] Screenshots

## Interface Screenshots
- `filename.png` - Description of what this shows

## Features Demonstrated
- `filename.png` - Description

## Videos
- `filename.mp4` - Description (duration, what's shown)
```

---

## Tips for Great Screenshots

✅ **DO:**
- Use clean, professional test data (no "asdf" or "test123")
- Show real functionality, not just empty states
- Capture during good lighting (screen brightness consistent)
- Include visual indicators of activity (progress bars, status lights)
- Demonstrate your most impressive features

❌ **DON'T:**
- Include personal information (emails, real names, addresses)
- Show error states unless demonstrating error handling
- Use offensive test data or inappropriate content
- Capture with notifications/distractions visible
- Rush - take time to make it look professional

---

## Priority Order (If Short on Time)

**High Priority (Must Have):**
1. D-Net Platform (4 screenshots min): Homepage, Dashboard, AI Chat, One key feature
2. DNetAether (3 screenshots min): Settings, Chat window, One demo
3. DNetCon (3 screenshots min): Dashboard, Pipeline builder, Program manager

**Medium Priority (Should Have):**
4. VirtualLense (3 screenshots): Setup mode, Controller, OCR demo
5. LangAdventure (2 screenshots): Dual-language display, Chat
6. DeckGen (3 screenshots): Upload, Processing, Results

**Low Priority (Nice to Have):**
7. AirControl (2 screenshots): Web UI, Gesture log
8. Choir (2 screenshots): Chat interface, Status

---

**Estimated Time:** 3-4 hours total for all 40+ captures
**When to Do This:** Dedicate a Saturday afternoon or break into 2-hour sessions

**Once Complete:** You'll have a visual portfolio to embed in:
- Portfolio.html website
- Project showcase folders
- LinkedIn featured media
- GitHub repository READMEs
- Interview presentations

Good luck! These screenshots will make your projects **tangible** to hiring managers.
