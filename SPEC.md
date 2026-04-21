# Shell — Mobile Gaming Platform Specification

## Concept & Vision

Shell is a premium mobile-first gaming platform featuring simple, transparent mini-games with clean mechanics. The experience feels like a high-end casino dashboard — dark, sleek, and confident. Every interaction should feel responsive and satisfying, with subtle audio feedback that confirms actions without being intrusive.

## Design Language

### Aesthetic Direction
Stake/Rainbet-inspired dark gaming dashboard with deep navy cards on near-black backgrounds. Premium, minimal, focused.

### Color Palette
- **Background**: #0a0e17 (deep blue-black)
- **Card Background**: #111827 (dark navy)
- **Primary Accent**: #3b82f6 (electric blue)
- **Secondary Text**: #64748b (muted blue-gray)
- **Success/Winning**: #22c55e (green)
- **Error/Negative**: #ef4444 (red)
- **Gold**: #fbbf24 (for #1 ranking)
- **Silver**: #94a3b8 (for #2 ranking)
- **Bronze**: #d97706 (for #3 ranking)
- **Text Primary**: #ffffff
- **Text Secondary**: #94a3b8

### Typography
- System font stack: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif
- Bold weights for headings
- Clean, readable sizes optimized for mobile

### Spatial System
- Card border-radius: 16-24px
- Button border-radius: 12-16px
- Padding: 12-20px for mobile
- Gap between elements: 12-16px

### Motion Philosophy
- Transitions: 200-300ms ease-out
- Micro-interactions for button states
- Coin flip: full 3D rotation animation
- Crash graph: smooth line drawing with crash moment

## Layout & Structure

### Header (Fixed)
- Left: Logo (blue rounded square with 3 dark waves) + "Shell" text
- Right: 4 icon buttons (Tournament, Sound, Wallet, Profile)
- All icons minimalistic, flat

### Main Screen
1. Hero Card: Online players badge, headline, description
2. Top Payouts Card: "Самые Платящие Игры" header with medal rankings
3. Game Cards: Single column, large rounded cards for each game

### Modals (Single Window System)
- Profile modal
- Deposit modal
- Withdraw modal
- Game modals (one at a time)

### Footer
- Minimal: "S" icon + "SHELL" text

## Features & Interactions

### Online Counter
- Range: 126-213 players
- Updates every 3 seconds by ±1-3
- Smooth number animation

### Games

#### 1. Mines (5x5 grid)
- Slider: 1-24 bombs
- Click cells to reveal
- Safe cells increase multiplier
- Bomb = round ends
- "Забрать" button to cash out (one-time use)

#### 2. CoinFlip
- Choose Heads (red O) or Tails (blue Р)
- Full flip animation (3D rotation)
- Coin rises, spins, lands

#### 3. Больше/Меньше (Higher/Lower)
- Dynamic odds based on current card
- Show chance % and multiplier for each option
- Higher card = multiplier for "Higher" decreases
- Lower card = multiplier for "Lower" decreases

#### 4. Crash
- Animated graph line growing
- Multiplier display
- Green line during growth
- Red crash moment

#### 5. Limbo
- User sets target multiplier
- Random result generated
- Win if result >= target

### Leaderboard
- Top 10 by coins
- Masked usernames (ano****176)
- Scaled coin amounts (hundreds of thousands)

### Monthly Raffle
- Auto-calculate days until month end (UTC)
- Dynamic "ОБНОВЛЕНИЕ ЧЕРЕЗ X ДНЕЙ"

### Profile
- Avatar, username, status
- Coins balance (starts at 3000)
- USD balance (always $0.00)
- localStorage persistence

### Sound System (Web Audio API)
- Click: soft tap
- Win: 2 soft thuds
- Lose: subtle scatter sound

## Component Inventory

### Buttons
- Primary: Blue background, white text
- Secondary: Dark background, light text
- Danger: Red accent for errors
- All have active/disabled states

### Cards
- Dark navy background
- Large border-radius (16-24px)
- Subtle hover states

### Modals
- Centered overlay
- Close button (X)
- Single window logic
- No blur effects on games

### Form Inputs
- Dark backgrounds
- Clear labels
- Mobile-friendly sizing

## Technical Approach

- Pure HTML/CSS/JavaScript
- localStorage for state persistence
- Web Audio API for sounds
- No external dependencies
- Centralized modal manager
- Click debouncing on all buttons
- Mobile-first responsive design
