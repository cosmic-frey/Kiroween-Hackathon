# Tamaghosty Development Notes

## Project Overview
Tamaghosty is a self-care companion app themed around a resurrected Tamagotchi ghost. It combines productivity tracking with interactive pet mechanics to encourage healthy habits.

## Key Features Implemented

### 1. Ghost Character Design
- **White body with purple-tipped tendrils**: Ghost has a white rounded body with curved, fading purple tendrils at the bottom
- **Purple glow effect**: Pulsing purple aura around the ghost
- **Curved tendrils**: Using SVG path clip-path for smooth, organic tendril shapes
- **Gradient fade**: Tendrils fade from white → purple → transparent at tips

### 2. Interactive Behaviors
- **Cursor following**: Ghost moves towards mouse cursor on home screen
- **Eye tracking**: Eyes follow cursor position with smooth movement
- **Body tilt**: Subtle 3D rotation effect based on cursor position
- **Mouth animations**: Opens when cursor hovers over ghost (when hungry)
- **Speech bubbles**: Contextual messages ("I'm hungry!", "Nom nom nom!", etc.)
- **Click responses**: Shows angry face and complaint when clicked while awake

### 3. Headphones (Study Mode)
- **Black headphones**: Appear when study timer is active
- **Positioned on sides**: Semicircle ear cups sit flush with sides of head
- **Strap over top**: Black band arcs over the ghost's head
- **No overlap**: Headphones positioned outside the white ghost body

### 4. Sleep System
- **Two modes**:
  - Study Mode: Sleeps 1 minute every 10 minutes (break reminder)
  - Normal Mode: Sleeps after 5 minutes of inactivity
- **Z's animation**: Floating Z's appear when sleeping
- **Wake up interaction**: Click to wake, shows angry message

### 5. Journal Feature
- **Book layout**: Two-page spread design
- **Left page**: Progress stats + daily prompt
- **Right page**: Full-page textarea for writing
- **Prompt system**: 100 reflective prompts that rotate
- **Entry saving**: Stores entries with date and prompt in localStorage
- **Photo scanning**: Can upload images to journal

### 6. Study Timer
- **Timer & Stopwatch modes**: Flexible time tracking
- **Gold glowing display**: Candle flicker effect on timer
- **Mini Tamaghosty icon**: Matches main ghost design in header
- **Stats display**: Shows progress in corner
- **Library background**: Atmospheric study environment

### 7. Ambient Effects (Home Screen)
- **Graveyard background**: Spooky cemetery theme
- **Flying bats**: Randomly spawn and fly across screen
- **Mysterious eyes**: Glowing red eyes appear randomly in background
- **Fog layers**: Multiple animated fog SVGs for atmosphere

## Technical Implementation

### State Management
- **localStorage**: Persists ghost stats, journal entries, and user preferences
- **React hooks**: useState and useEffect for all interactive behaviors
- **Mouse tracking**: Global mouse position tracked in App.jsx, passed to Tamaghosty

### Animation Techniques
- **CSS animations**: Floating, glowing, blinking, sleeping
- **Transform-based movement**: Smooth cursor following with translate()
- **3D transforms**: Body tilt effect with rotateX/rotateY
- **Clip-path**: Curved tendrils using SVG path syntax
- **Gradients**: Fading effects on tendrils and glow

### Component Structure
```
App.jsx (Main container)
├── Tamaghosty.jsx (Interactive ghost character)
├── StudyTimer.jsx (Pomodoro-style timer)
├── Hydration.jsx (Water tracking)
├── Meditation.jsx (Breathing exercises)
├── Journal.jsx (Reflective writing)
└── FoodLog.jsx (Meal tracking)
```

## Design Philosophy
1. **Playful but purposeful**: Fun ghost theme encourages engagement with self-care
2. **Non-judgmental**: Ghost gets tired/hungry but never punishes user
3. **Ambient presence**: Ghost is always visible, providing companionship
4. **Reward-based**: Completing activities "feeds" the ghost, creating positive reinforcement
5. **Nostalgic**: Tamagotchi reference appeals to millennials/Gen Z

## Future Improvements to Consider
- [ ] Fix cursor following (currently not moving smoothly)
- [ ] Add more ghost expressions/animations
- [ ] Implement achievement system
- [ ] Add sound effects
- [ ] Create mobile-responsive design
- [ ] Add customization options (ghost colors, accessories)
- [ ] Implement streak tracking
- [ ] Add social features (share progress)

## Recent Fixes
- ✅ **Cursor following**: Fixed by using requestAnimationFrame and proper transform calculation
- ✅ **Syntax error**: Removed duplicate closing bracket in useEffect
- ✅ **Transform positioning**: Combined centering transform with position offset using calc()

## Known Issues
- Eye tracking could be more responsive
- Speech bubbles need cooldown refinement

## Code Comments
All major components now have comprehensive comments explaining:
- Purpose of each state variable
- How effects work and why they're needed
- Design decisions and their rationale
- Interaction flows and user experience goals

### Files with Detailed Comments:
- ✅ **App.jsx**: Main app structure, state management, ambient effects
- ✅ **Tamaghosty.jsx**: Ghost character behavior and interactions
- ✅ **Tamaghosty.css**: Visual styling for ghost (body, tendrils, eyes, headphones)
- ✅ **StudyTimer.jsx**: Timer/stopwatch logic and modes
- ✅ **Journal.jsx**: Book layout and entry system
- ✅ **Feature.css**: Shared styles for all feature components

### Comment Maintenance Policy:
**When making changes, always update comments to reflect:**
1. What the code does
2. Why it's needed
3. How it fits into the overall design
4. Any gotchas or important details
