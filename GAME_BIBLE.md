# Game Bible: The Hunted

## Name
**the-hunted**

## Tagline
*Something follows. It never stops. Run.*

## What is the player?
A lost worker who died in the facility. You don't remember dying — only the need to run, to escape, to find the surface. You are a ghost who doesn't know it's a ghost.

## What does the world feel like?
The cold is absolute — not just temperature, but emptiness. Metal groans beneath your feet. Water drips somewhere distant. The air tastes of rust and decay. And behind you — always behind you — something massive shifts in the dark.

## Emotional target
**Dread** — not sharp fear, but the slow certainty that something is coming and you cannot stop it.

## Color palette
- **Void Black** (#0a0a0f) — player silhouette
- **Cold Steel** (#2a2d35) — foreground platforms
- **Factory Grey** (#1a1d25) — mid-ground elements
- **Deep Fog** (#0d1018) — background layers
- **Accent: Amber Glow** (#ff6b1a) — single distant light, a dying lamp

## Visual reference
*Looks like Limbo meets Inside: pure silhouette against layered fog, industrial structures barely visible, the hunter a massive dark shape that swallows light.*

## Bloom
Subtle (0.4 strength). Not glowing — the amber light should feel like dying ember, not neon.

## Music identity
- **Safe state**: A single low sine tone (cello-like), held for 4-6 seconds, then silence. A second tone fades in after a pause. Sparse. Like breathing in a dark room.
- **Danger state**: All music drops out completely. A heartbeat takes over — low MembraneSynth thud at 75bpm. Unmistakably close.
- **Death**: One final low note, held too long, then cut to silence.
- **Area transition**: A brief ascending tone, then silence.

## Music↔gameplay
- Silence is the baseline
- When hunter is < 30% distance: heartbeat begins, music stops
- When hunter is > 50% distance: one note returns, tentative
- When hunter is > 70% distance: full sparse drone returns

## 5 Level/Area Names
1. **The Entry** — dim corridor, broken lights, gentle introduction
2. **The Machines** — grinding gears in background, conveyor obstacles
3. **The Flood** — rising water below, platform hopping
4. **The Dark** — lights fail, only player rim-light, hunter's eyes visible
5. **The End** — full darkness, water to waist, the exit door far ahead

## The Moment
*The player reaches the final corridor. Water at chest height. The hunter is right behind. A single amber light flickers above the exit door. You can see it. You can almost touch it. But the heartbeat is deafening now.*

## Lore (3 sentences)
The factory was sealed fifty years ago after the accident. You were a maintenance worker who got trapped in the lower levels. Now something else lives here — and it remembers you.

---

## Technical Notes

### Mobile Controls
- Left/Right virtual buttons (bottom-left)
- Jump button (bottom-right)
- Use Pointer Events: `pointerdown`, `pointerup`
- Touch-action: none on canvas

### Hunter Behavior
- Starts at 80% screen distance (appears far)
- Gradually closes gap at varying pace
- Speed increases per area (Area 3+ becomes threatening)
- If player stops moving, hunter closes faster

### Areas
Each area ~500 units long, increasing difficulty
- Area 1: basic gaps
- Area 2: conveyors + gaps
- Area 3: water (must stay on platforms) + gaps
- Area 4: duck obstacles + dark
- Area 5: water + complex platforming + hunter close

### Distance Counter
Small text, top-right corner: "42m" (updates every second based on x position)

### Death
- Player frozen
- Camera zooms slowly toward player
- Fade to black over 3 seconds
- "CAUGHT" text + furthest distance + "TAP TO RETRY"

### Win
- After Area 5 exit door
- Fade to white
- "ESCAPED" text
- Credits roll: "A game by Nishi Vector / Three.js + Tone.js / 2026"
