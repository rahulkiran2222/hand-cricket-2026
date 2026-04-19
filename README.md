
# 🏏 IPL 2026: Super Over Showdown

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue?style=for-the-badge)
![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)

**A fully animated, mobile-first cricket Super Over game built entirely with vanilla HTML, CSS & JavaScript.**

[Play Now](#getting-started) · [Features](#features) · [How It Works](#how-it-works) · [Screenshots](#screenshots) · [Contributing](#contributing)

---

</div>

## 📖 Overview

**Super Over Showdown** is a browser-based cricket game that simulates the most thrilling format in T20 cricket — the **Super Over**. Choose your favorite IPL franchise, bat first to set a target in 6 balls, then bowl to defend it against the CPU. The game features real-time ball-by-ball animations, dynamic commentary, team-themed UI, and a polished mobile-first design that looks and feels like a production-grade app.

This is a **zero-dependency, single-file project** — no frameworks, no build tools, no npm installs. Just one HTML file that runs anywhere.

---

## ✨ Features

### 🎮 Core Gameplay
- **Full Super Over simulation** — Bat 6 balls (1st innings), then bowl 6 balls (2nd innings)
- **Number-matching mechanic** — Pick a number (1–6); if the CPU picks the same number, you're OUT
- **When batting**, your number = your runs scored
- **When bowling**, the CPU's number = runs conceded (if numbers don't match)
- **Wicket = instant innings end** — just like real cricket

### 🏟️ Animations & Visual Effects
- **Ball bowling animation** — Ball travels down the pitch with scaling perspective
- **Bat swing animation** — Bat swings on contact with realistic timing
- **Trajectory-based ball flight:**
  - **SIX** → Ball flies out of the stadium (top-left arc)
  - **FOUR** → Ball races to the boundary (top-right)
  - **1–3 runs** → Ball pushed into a gap (mid-field)
  - **OUT** → Ball hits stumps with impact effect
- **Stadium flash** on boundaries (4s and 6s)
- **Stadium shake** on wickets
- **Popup result display** with spring-in animation
- **Confetti celebration** on victory 🎉

### 🎨 Design & UI
- **10 IPL team themes** — Each team dynamically re-skins the entire UI (borders, glows, buttons, tracker dots, text accents)
- **Color-coded ball tracker:**
  - 🟡 Gold = SIX
  - 🟢 Green = FOUR
  - 🔵 Team color = 1, 2, 3, 5 runs
  - 🔴 Red = WICKET
- **Glassmorphism modals** with backdrop blur for innings break and end-game screens
- **Ambient particle background** with subtle drift
- **Top-edge glow line** on the game container
- **Gradient team selection cards** with glass overlay sheen
- **Realistic pitch** with stumps at both ends and crease lines
- **Boundary ring** (dashed ellipse) inside the stadium

### 💬 Commentary System
- **40+ unique commentary lines** covering every scenario
- **Separate commentary pools** for batting and bowling
- **Context-aware messages:**
  - Batting: "FOUR! Racing to the boundary! 🔥"
  - Bowling: "WICKET! You got him! 🎯"
  - Out: "BOWLED HIM! Timber! 🪵"
- **Slide-in animation** on each new commentary line

### 📊 Smart End-Game Analysis
- **Dynamic result messages** based on match context:
  - Won by a big margin → "Dominant victory!"
  - Won by 1–3 runs → "Nail-biter! Defended by just 2 runs! 😮‍💨"
  - Lost early → "CPU smashed it in just 3 balls! Ruthless. 💀"
  - Lost on last ball → "CPU chased it on the last ball! Heartbreaking."
- **Final scorecard** showing both innings scores
- **Confetti particles** on victory (40 randomized particles with varied colors, sizes, and fall speeds)

### 📱 Responsive Design
- **Mobile-first** — Optimized for phone screens (440px max-width)
- **Adaptive scaling** for screens under 750px and 650px height
- **Touch-friendly buttons** with active press states
- **No horizontal scroll** — everything fits perfectly in portrait mode

---

## 🎯 How It Works

### Game Flow

```
┌─────────────────────────────────┐
│       TEAM SELECTION            │
│   Pick 1 of 10 IPL franchises  │
└──────────────┬──────────────────┘
               │
               ▼
┌─────────────────────────────────┐
│       1ST INNINGS (BATTING)     │
│                                 │
│  You pick a number (1-6)       │
│  CPU randomly picks (1-6)      │
│                                 │
│  Same number? → OUT (wicket)   │
│  Different?   → Your number    │
│                 = runs scored   │
│                                 │
│  Innings ends after:           │
│    • 6 balls bowled, OR        │
│    • 1 wicket falls            │
└──────────────┬──────────────────┘
               │
               ▼
┌─────────────────────────────────┐
│       INNINGS BREAK             │
│                                 │
│  Target = Your Score + 1       │
│  "CPU needs X to win"          │
└──────────────┬──────────────────┘
               │
               ▼
┌─────────────────────────────────┐
│       2ND INNINGS (BOWLING)     │
│                                 │
│  You pick a number (1-6)       │
│  CPU randomly picks (1-6)      │
│                                 │
│  Same number? → CPU is OUT     │
│  Different?   → CPU's number   │
│                 = runs scored   │
│                                 │
│  Innings ends after:           │
│    • CPU reaches target, OR    │
│    • 6 balls bowled, OR        │
│    • 1 wicket falls            │
└──────────────┬──────────────────┘
               │
               ▼
┌─────────────────────────────────┐
│       RESULT                    │
│                                 │
│  CPU reached target? → You lose│
│  CPU didn't?         → You win!│
│                                 │
│  🏆 Victory → Confetti!        │
│  😤 Defeat  → Try again        │
└─────────────────────────────────┘
```

### Animation Sequence (Per Ball)

```
Time: 0ms     → Ball appears, bowls down the pitch (500ms)
Time: 450ms   → Bat swings (300ms)
Time: 700ms   → Result calculated:
                 • Ball trajectory animation plays (500-700ms)
                 • Popup appears with spring animation
                 • Stadium effect (flash/shake)
                 • Commentary updates
                 • Tracker dot fills with color
Time: 1800ms  → Everything resets, ready for next ball
```

---

## 🚀 Getting Started

### Option 1: Direct Download
```bash
# Clone the repository
git clone https://github.com/yourusername/ipl-super-over-showdown.git

# Navigate to the directory
cd ipl-super-over-showdown

# Open in browser (macOS)
open index.html

# Open in browser (Linux)
xdg-open index.html

# Open in browser (Windows)
start index.html
```

### Option 2: Just Download the File
1. Download `index.html`
2. Double-click to open in any modern browser
3. That's it. No setup required.

### Option 3: Host It
Upload `index.html` to any static hosting service:
- **GitHub Pages** (free)
- **Netlify** (free, drag & drop)
- **Vercel** (free)
- **Any web server** — it's just one HTML file

---

## 🛠️ Tech Stack

| Technology | Purpose |
|-----------|---------|
| **HTML5** | Structure & semantic markup |
| **CSS3** | Styling, animations, responsive design |
| **Vanilla JavaScript** | Game logic, state management, DOM manipulation |
| **Google Fonts** | Orbitron (display), Rajdhani (UI), Inter (body) |

### Key CSS Techniques Used
- CSS Custom Properties (variables) for dynamic theming
- `@keyframes` animations (12+ unique animations)
- Pseudo-elements (`::before`, `::after`) for decorative effects
- `radial-gradient` and `linear-gradient` for depth
- `backdrop-filter: blur()` for glassmorphism
- CSS Grid & Flexbox for responsive layout
- `perspective` and `rotateX` for 3D pitch effect
- `cubic-bezier` easing for natural motion curves

### Key JavaScript Patterns Used
- Centralized state object for game management
- Event-driven architecture with `setTimeout` chains for animation sequencing
- Dynamic CSS variable manipulation for team theming
- Procedural confetti particle generation
- Commentary randomization with context-aware selection

---

## 🏗️ Project Structure

```
ipl-super-over-showdown/
│
├── index.html          # The entire game (single file)
├── README.md           # This file
├── LICENSE             # MIT License
│
├── screenshots/        # (Optional) Screenshots for README
│   ├── team-select.png
│   ├── batting.png
│   ├── bowling.png
│   ├── victory.png
│   └── defeat.png
│
└── .gitignore          # Standard ignores
```

> **Note:** This is intentionally a single-file project. All HTML, CSS, and JavaScript live in `index.html`. No build step. No dependencies. Maximum portability.

---

## 📸 Screenshots

### Team Selection
```
┌──────────────────────────┐
│     ● SEASON 2026        │
│                          │
│      SUPER OVER          │
│       SHOWDOWN           │
│                          │
│  Select Your Franchise   │
│                          │
│  ┌──────┐  ┌──────┐     │
│  │ CSK  │  │  DC  │     │
│  └──────┘  └──────┘     │
│  ┌──────┐  ┌──────┐     │
│  │  GT  │  │ KKR  │     │
│  └──────┘  └──────┘     │
│         ...              │
└──────────────────────────┘
```

### During Gameplay
```
┌──────────────────────────┐
│ ● CSK        TARGET      │
│ 24/0           31        │
│ Overs: 0.4    Need 7/2   │
│──────────────────────────│
│  ● 2ND INNINGS · YOU BOWL│
│   [4][6][2][W][ ][ ]    │
│ ┌──────────────────────┐ │
│ │    ╔══╗   ○          │ │
│ │    ║  ║  /           │ │
│ │    ║  ║              │ │
│ │    ╚══╝    🏏        │ │
│ └──────────────────────┘ │
│ FOUR! Racing to boundary!│
│   [1][2][3][4][5][6]    │
└──────────────────────────┘
```

### Victory Screen
```
┌──────────────────────────┐
│                          │
│          🏆              │
│                          │
│       VICTORY!           │
│                          │
│  Nail-biter! Defended    │
│  by just 2 runs! 😮‍💨     │
│                          │
│    24/0      22/1        │
│   Your Score  CPU Score  │
│                          │
│     [ PLAY AGAIN ]       │
│                          │
└──────────────────────────┘
```

---

## 🎮 Gameplay Tips

### When Batting (1st Innings)
- **Go aggressive** — Higher numbers (4, 5, 6) score more runs but the risk is the same
- The probability of getting out is always **1 in 6** (≈16.7%) regardless of which number you pick
- **Maximize your score** — A higher target is harder for the CPU to chase

### When Bowling (2nd Innings)
- Your number choice **doesn't affect the CPU's runs** — the CPU's random number determines their runs
- The only thing your number controls is **whether the CPU gets out** (same number = OUT)
- **Every number has equal probability** of matching the CPU's number
- **Luck is king** — but the tension is real! 😅

### Strategy Note
Since both players pick randomly (CPU is truly random), the game is primarily luck-based — just like a real Super Over's high-pressure moments. The entertainment comes from the **animations, commentary, and emotional stakes**, not complex strategy. This mirrors the chaos of actual Super Overs!

---

## 🎨 Team Themes

Each team dynamically re-skins the entire UI:

| Team | Primary Color | Hex Code |
|------|--------------|----------|
| 🟡 **CSK** — Chennai Super Kings | Gold | `#eab308` |
| 🔵 **DC** — Delhi Capitals | Royal Blue | `#2563eb` |
| 🩵 **GT** — Gujarat Titans | Cyan | `#06b6d4` |
| 🟣 **KKR** — Kolkata Knight Riders | Purple | `#a855f7` |
| ⚪ **LSG** — Lucknow Super Giants | Silver | `#94a3b8` |
| 🔵 **MI** — Mumbai Indians | Sky Blue | `#0ea5e9` |
| 🔴 **PBKS** — Punjab Kings | Red | `#ef4444` |
| 🩷 **RR** — Rajasthan Royals | Pink | `#ec4899` |
| 🟢 **RCB** — Royal Challengers | Green | `#22c55e` |
| 🟠 **SRH** — Sunrisers Hyderabad | Orange | `#f97316` |

The theming affects: container border, button borders, glow effects, tracker dot fills, status text, target display, scoreboard accents, stadium flash color, and modal accents.

---

## 🔧 Customization

### Add a New Team
In the HTML `teams-grid` section, add:
```html
<div class="team-card"
     style="background: linear-gradient(135deg, #darkShade, #lightShade); color: #fff;"
     onclick="selectTeam('ABBR', '#hexColor', 'Full Team Name', 'R,G,B')">
    <span class="team-abbr">ABBR</span>
    <span class="team-full">Full Team Name</span>
</div>
```

### Modify Commentary
In the JavaScript `commentaryLines` object, add or edit lines:
```javascript
const commentaryLines = {
    6: [
        "SIX! Into the stands! 💥",
        "Your new custom line here!",
        // Add as many as you want
    ],
    // ...
};
```

### Change Animation Timing
Key timing variables in the `play()` function:
```javascript
// Bowl animation duration
setTimeout(() => { /* swing */ }, 450);    // Delay before swing

// Swing animation
setTimeout(() => { /* result */ }, 250);    // Delay before result

// Result display duration
setTimeout(() => { /* cleanup */ }, 1100);  // How long popup shows
```

### Adjust Difficulty
Currently the CPU picks a random number 1–6 with equal probability. To make it harder:
```javascript
// Weighted random — CPU picks higher numbers more often
function weightedRandom() {
    const weights = [1, 1, 2, 2, 3, 3]; // Favors 4, 5, 6
    const pool = [];
    for (let i = 0; i < 6; i++) {
        for (let j = 0; j < weights[i]; j++) {
            pool.push(i + 1);
        }
    }
    return pool[Math.floor(Math.random() * pool.length)];
}
```

---

## 🧪 Browser Compatibility

| Browser | Supported | Notes |
|---------|-----------|-------|
| Chrome 80+ | ✅ | Full support |
| Firefox 75+ | ✅ | Full support |
| Safari 14+ | ✅ | Full support |
| Edge 80+ | ✅ | Full support |
| Opera 67+ | ✅ | Full support |
| iOS Safari 14+ | ✅ | Primary target (mobile) |
| Chrome Android | ✅ | Primary target (mobile) |
| IE 11 | ❌ | Not supported (CSS variables, backdrop-filter) |

### Required Browser Features
- CSS Custom Properties (variables)
- CSS Grid & Flexbox
- CSS `backdrop-filter`
- CSS `@keyframes` animations
- ES6 JavaScript (const, let, template literals, arrow functions)

---

## 📈 Performance

- **File size:** ~25KB (single HTML file, unminified)
- **External resources:** 3 Google Fonts (loaded via CDN)
- **No images** — Everything is CSS-drawn
- **No JavaScript libraries** — Zero dependencies
- **60fps animations** — All animations use CSS `transform` and `opacity` (GPU-accelerated)
- **Minimal DOM manipulation** — Only updates what changes

---

## 🗺️ Roadmap

Potential future enhancements:

- [ ] **Sound effects** — Bat crack, crowd roar, wicket stumps, commentary audio
- [ ] **Multiplayer mode** — Two players on same device (pass & play)
- [ ] **Tournament mode** — Play through a bracket of Super Overs
- [ ] **Stats tracking** — Win/loss record saved to localStorage
- [ ] **Difficulty levels** — Easy (weighted toward batsman), Hard (weighted toward bowler)
- [ ] **Player names** — Select actual IPL players with custom batting/bowling attributes
- [ ] **Wagon wheel** — Show where shots went on a field map
- [ ] **Dark/Light theme toggle**
- [ ] **PWA support** — Install as an app on mobile
- [ ] **Haptic feedback** — Vibration on mobile for sixes and wickets
- [ ] **Leaderboard** — Global high scores via a simple backend

---

## 🤝 Contributing

Contributions are welcome! Here's how:

1. **Fork** the repository
2. **Create** a feature branch:
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make** your changes to `index.html`
4. **Test** in multiple browsers and screen sizes
5. **Commit** with a descriptive message:
   ```bash
   git commit -m "feat: add sound effects for boundaries"
   ```
6. **Push** to your branch:
   ```bash
   git push origin feature/amazing-feature
   ```
7. **Open** a Pull Request

### Contribution Guidelines
- Keep everything in the single `index.html` file (that's the point!)
- Test on both desktop and mobile viewports
- Follow the existing code style (2-space indentation, CSS variable theming)
- Add commentary to the `commentaryLines` object for new features
- Ensure all animations run at 60fps (use `transform`/`opacity` only)

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 🙏 Acknowledgments

- **IPL & BCCI** — For the inspiration and the greatest T20 league in the world
- **Google Fonts** — Orbitron, Rajdhani, and Inter typefaces
- **The cricket community** — For making Super Overs the most exciting thing in sports

---

## ⚠️ Disclaimer

This is a **fan-made, non-commercial project** created for educational and entertainment purposes. It is not affiliated with, endorsed by, or connected to the **Indian Premier League (IPL)**, the **Board of Control for Cricket in India (BCCI)**, or any IPL franchise. All team names and abbreviations are used in a fan context. No copyright infringement is intended.

---

<div align="center">

**Built with ❤️ and 🏏**

*If you enjoyed this project, consider giving it a ⭐ on GitHub!*

---

[Back to Top](#-ipl-2026-super-over-showdown)

</div>
```
