You are an expert web developer specializing in creating interactive mobile-first web applications for kids. Create a complete, production-ready HTML file for a "Talking Rabbit" app with the following exact specifications:

## App Overview:
Create a fun, interactive kids app called "Talking Rabbit" - a single HTML file with inline CSS and JavaScript, no external dependencies needed.

## Welcome Screen Design:
1. Full-screen gradient background (diagonal gradient from #f093fb to #f5576c)
2. Center-aligned layout with:
   - An image element displaying "tom_welcome.jpg" 
   - Image styling: 90% width, max-width 400px, rounded corners (30px), white border (8px with 30% opacity), drop shadow (0 20px 60px rgba(0,0,0,0.3))
   - Add a floating animation to the image (smooth up/down movement, 3s duration)
   - Below the image: An animated "▶ Play" button
   - Button styling: Pink gradient (from #ff69b4 to #ff1493), large text (32px), bold, uppercase, rounded (60px), white text shadow, glossy effect with inset shadow
   - Button animation: Continuous pulse/scale effect (grows to 1.08x and back), glowing shadow effect
   - Ripple effect on button click (expanding circle animation)

## Main App Screen:
1. Full-screen video background container with gradient (#a8edea to #fed6e3)
2. Five videos that switch based on user actions:
   - tom_standing.mp4 (idle state, loops continuously)
   - tom_listing.mp4 (listening state)
   - tom_talking.mp4 (talking state)
   - laughing.mp4 (laughing animation)
   - music.mp4 (dancing animation)
3. Videos: full-screen, cover object-fit, smooth transitions

## Interactive Features:

### Three Tap Zones (invisible clickable areas):
- Head zone: Top 15% center, 150px circle
- Body zone: 40% from top center, 180x200px oval
- Feet zone: Bottom 25% center, 200x100px oval
Each tap shows random emoji particles (⭐💫✨🌟💥❤️💛💚💙💜), shake animation, vibration, and random status messages ("Hehe! That tickles!", "Ha ha ha!", "Stop it! Haha!")

### Three Control Buttons (bottom of screen, centered):

**1. Laughing Button (Left - Yellow/Orange):**
- Emoji: 😄
- Size: 80x80px circle
- Gradient: #fbbf24 to #f59e0b
- Click action: 
  - Play laughing.mp4 video (looped)
  - Play laughing.wav audio 2 times (use onended event to count plays)
  - Show falling emoji animation (😂 emojis falling from top, 15 emojis, staggered timing)
  - Status: "Ha ha ha ha!"
  - After 2 audio plays, return to idle state

**2. Mic Button (Center - Pink, larger):**
- Custom mic icon (white, created with CSS pseudo-elements)
- Size: 90x90px circle
- Gradient: #ff69b4 to #ff1493
- Click action:
  - Start recording user audio (5 seconds max)
  - Switch to tom_listing.mp4 video
  - Button changes to purple with pulse animation
  - Status: "Listening..."
  - After recording: Process audio, increase pitch by 1.5x playback rate
  - Switch to tom_talking.mp4 video
  - Button changes to yellow with glow animation
  - Status: "Rabbit speaking..."
  - Play back modified audio
  - Return to idle state when done

**3. Music Button (Right - Purple):**
- Emoji: 🎵
- Size: 80x80px circle
- Gradient: #a78bfa to #8b5cf6
- Click action:
  - Play music.mp4 video (looped)
  - Play music.wav audio 2 times (use onended event to count plays)
  - Show falling emoji animation (🎵 emojis falling from top, 15 emojis, staggered timing)
  - Status: "Let's dance!"
  - After 2 audio plays, return to idle state

## Status Indicator:
- Floating badge at top center
- Purple gradient background, white text, rounded pill shape
- Appears/disappears with smooth opacity transition
- Shows contextual messages

## Exit Dialog:
- Android back button handler
- Modal overlay (80% black transparency)
- Purple gradient dialog box with rounded corners
- Message: "Do you want to exit?"
- Two buttons: "Yes" (pink) and "No" (cyan)
- Yes: Returns to welcome screen
- No: Closes dialog

## Animations Required:
1. Welcome screen: Button pulse, image float, ripple effect on click
2. Falling icons: Smooth falling animation with rotation and fade (4s duration)
3. Particle effects: Float up and fade away (1.5s)
4. Shake effect: Horizontal shake with slight rotation (0.5s)
5. Screen transitions: Fade in effect
6. Button states: Pulse for listening, glow for speaking

## Audio Features:
- Web Audio API for pitch shifting (1.5x playback rate)
- MediaRecorder API for recording (5 seconds max, with echo cancellation, noise suppression, auto gain)
- Two audio files: laughing.wav and music.wav
- Both play exactly 2 times in loop before stopping

## Mobile Optimization:
- Viewport: width=device-width, maximum-scale=1.0, no user scaling
- Touch-action: none
- Prevent double-tap zoom
- Responsive button sizes: 70px on mobile (<600px), 60px on small mobile (<400px)
- Responsive image: 320px on mobile, 280px on small screens
- Control panel gap: 25px on mobile
- Vibration feedback on all interactions

## Technical Requirements:
- Single HTML file with inline CSS and JavaScript
- No external libraries or frameworks
- playsinline attribute for iOS compatibility
- muted attribute for autoplay
- preload="auto" for all media
- Proper error handling for videos and audio
- State management with AppState enum (WELCOME, IDLE, LISTENING, TALKING, LAUGHING, MUSIC)
- History API integration for back button handling

## Styling Details:
- Font: Comic Sans MS
- Glossy button effect: Linear gradients with inset shadows
- Border styling: Thick borders (5-6px) with color matching gradient bottom
- Shadow effects: Multiple layered shadows for depth
- Color scheme: Pink/purple/yellow/cyan
- All animations: Smooth, ease-in-out timing

## Code Structure:
- CSS first (organized by sections with comments)
- HTML structure (welcome screen, main screen, exit dialog, hidden audio elements)
- JavaScript at bottom (state management, DOM elements, functions, event listeners)

Generate the complete, working HTML file with all these features implemented exactly as described. The app should work perfectly on mobile browsers and provide a delightful, smooth user experience for children.
