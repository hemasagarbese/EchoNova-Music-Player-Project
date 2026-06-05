# 🎵 EchoNova – Indian Music Universe

> A futuristic, multi-page Indian music streaming platform inspired by Spotify, Apple Music, and JioSaavn — built as a Frontend Development Internship project.

![React](https://img.shields.io/badge/React-18.x-61DAFB?logo=react) ![Vite](https://img.shields.io/badge/Vite-5.x-646CFF?logo=vite) ![CSS3](https://img.shields.io/badge/CSS3-Advanced-1572B6?logo=css3) ![License](https://img.shields.io/badge/License-MIT-green)

---

## 👨‍💻 Intern Information

| Field              | Details                               |
|--------------------|---------------------------------------|
| **Intern ID**      | CT08FDS12984                          |
| **Full Name**      | Bese Hema Sagar                       |
| **Internship**     | June 2026 – July 2026 (CodTech IT)   |
| **Project Name**   | EchoNova – Indian Music Universe      |
| **Repository**     | `codtech-echonova-music-player`       |

---

## 🌟 Overview

**EchoNova** is a premium, fully responsive multi-page music streaming application covering the 5 major Indian film industries. It features real-time audio playback, a persistent bottom mini-player, a Top Songs archive spanning 10 years (2016–2025), glassmorphism UI, neon dark mode, animated visualizers, Favorites/History persistence via `localStorage`, and a Web Audio API synthesizer fallback.

---

## 🚀 Features

### 🎬 Film Industry Pages
- **Tollywood** (Telugu) — 50 tracks, categorised by Trending / Romantic / Evergreen
- **Kollywood** (Tamil) — 50 tracks, including Tamil chart-toppers
- **Mollywood** (Malayalam) — 50 tracks, featuring soulful indie compositions
- **Bollywood** (Hindi) — 50 tracks, Bollywood blockbuster hits
- **Sandalwood** (Kannada) — 50 tracks, Kannada cinema music

### 📅 Top Songs Archive (2016–2025)
- **Top 10 songs per industry per year** — 50 songs per year, 500 total entries
- Year selector tabs + industry filter pills
- Global search across all archive entries
- Seeded with real hit songs (e.g. *Naatu Naatu*, *Srivalli*, *Satranga*, *Darshana*)

### 🎧 Global Music Player
- **Persistent bottom mini-player** — stays visible while navigating any page
- **Full-screen player page** at `/player` with rotating vinyl, glowing rings & audio visualizer
- Play / Pause / Next / Previous / Seek controls
- Shuffle mode & Loop mode
- Volume slider + Mute toggle
- **Web Audio API synth fallback** — if MP3 URLs fail (CORS/network), a pentatonic synthesizer takes over automatically

### ❤️ User Data (LocalStorage Persistence)
- **Favorites** — add/remove any song via the heart icon; persists across reloads
- **Recently Played** — last 15 songs auto-saved and shown on the Home page
- **Theme preference** — Dark/Light mode toggle persisted

### 🎨 UI/UX & Visual Design
- **Glassmorphism panels** — `backdrop-filter: blur()` with translucent borders
- **Neon cyberpunk theme** — Purple, Electric Blue, Hot Pink, Amber palette
- **Light Mode** — elegant bright alternative toggled from the Navbar
- **Cursor Glow** — radial neon spotlight tracks mouse position
- **Floating Music Icons** — ambient 🎵🎶♪♫🎧 particles drift up in the background
- **Equalizer wave animations** in the Home hero and player visualizer
- **Rotating vinyl artwork** while a track is playing

---

## 🗂️ Project Structure

```
src/
├── components/
│   ├── CursorGlow.jsx       # Mouse-tracking radial glow
│   ├── FloatingIcons.jsx    # Ambient floating music icons
│   ├── MusicCard.jsx        # Reusable song card with hover effects
│   ├── Navbar.jsx           # Sticky top nav with search & theme toggle
│   ├── Player.jsx           # Persistent bottom mini-player bar
│   ├── Playlist.jsx         # Sidebar track queue list
│   └── Visualizer.jsx       # Equalizer bar animation component
├── context/
│   └── MusicPlayerContext.jsx  # Global state + Audio + Synth fallback
├── data/
│   ├── tollywoodSongs.js    # 50 Telugu songs
│   ├── kollywoodSongs.js    # 50 Tamil songs
│   ├── mollywoodSongs.js    # 50 Malayalam songs
│   ├── bollywoodSongs.js    # 50 Hindi songs
│   ├── sandalwoodSongs.js   # 50 Kannada songs
│   └── topSongs.js          # 500 archive songs (10 per industry × 10 years)
├── pages/
│   ├── Home.jsx             # Hero, industry cards, trending, favorites, history
│   ├── TopSongs.jsx         # Archive with year/industry filters + search
│   ├── Tollywood.jsx        # Telugu industry page
│   ├── Kollywood.jsx        # Tamil industry page
│   ├── Mollywood.jsx        # Malayalam industry page
│   ├── Bollywood.jsx        # Hindi industry page
│   ├── Sandalwood.jsx       # Kannada industry page
│   └── PlayerPage.jsx       # Full-screen music player experience
├── App.jsx                  # Router + layout shell
├── App.css                  # All global styles, animations, themes
└── index.css                # CSS variables & root reset
```

---

## 🛠️ Technology Stack

| Technology        | Purpose                                      |
|-------------------|----------------------------------------------|
| **React 18**      | Component-based UI & state management        |
| **React Router v6** | Multi-page SPA navigation                  |
| **Vite**          | Lightning-fast development build tool        |
| **React Icons**   | Icon library (FontAwesome subset)            |
| **Web Audio API** | Synthesizer fallback for playback            |
| **localStorage**  | Favorites, recently played & theme storage   |
| **CSS3**          | Glassmorphism, keyframe animations, themes   |

---

## ⚙️ Installation & Setup

```bash
# 1. Clone the repository
git clone https://github.com/BeseHemaSagar/codtech-echonova-music-player.git
cd codtech-echonova-music-player

# 2. Install dependencies
npm install

# 3. Start the development server
npm run dev

# 4. Build for production
npm run build
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

---

## 📱 Pages & Routes

| Route          | Page                   | Description                                    |
|----------------|------------------------|------------------------------------------------|
| `/`            | Home                   | Hero, industry cards, trending, favorites      |
| `/top-songs`   | Top Songs Archive      | Year × Industry × Search filtered list         |
| `/tollywood`   | Tollywood              | 50 Telugu songs in 3 categories                |
| `/kollywood`   | Kollywood              | 50 Tamil songs in 3 categories                 |
| `/mollywood`   | Mollywood              | 50 Malayalam songs in 3 categories             |
| `/bollywood`   | Bollywood              | 50 Hindi songs in 3 categories                 |
| `/sandalwood`  | Sandalwood             | 50 Kannada songs in 3 categories               |
| `/player`      | Full Player            | Full-screen player with visualizer & queue     |

---

## 🎯 Architecture Highlights

### Global Playback State
A single `MusicPlayerContext` wraps the entire app, holding one `<audio>` element at the root. This ensures **music never interrupts during page navigation** — identical to how Spotify maintains continuous playback.

### Web Audio API Fallback
If the remote MP3 source fails to load (CORS/network issue), the app automatically switches to `isSynthMode` and plays a **pentatonic melody using oscillators** — ensuring the audio visualizer and playback controls continue working seamlessly.

### Top Songs Archive Logic
```
generateTopSongs():
  for each YEAR (2016–2025):
    for each INDUSTRY (Tollywood, Kollywood, Mollywood, Bollywood, Sandalwood):
      generate Top 10 songs → 50 songs/year × 10 years = 500 entries total
```

---

## 📜 License

This project is developed as part of a **CodTech IT Solutions Frontend Internship** and is for educational/portfolio use.

---

*Built with ❤️ by Bese Hema Sagar | CodTech Internship 2026*
#   E c h o N o v a - M u s i c - P l a y e r - P r o j e c t  
 