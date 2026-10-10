# Soccer Quest ⚽ — Think Fast, Play Brave!

A free, mobile-friendly mini-game for young soccer players (roughly ages 7–9) to practice brave, safe defending and fast, smart attacking decisions.

**Play online (after GitHub Pages is activated):** https://chandus-garage.github.io/soccer-game/

## Five missions

1. **Brave Defender** — close the gap, slow down, stay in front, and challenge safely.
2. **Win It & Go** — steal, look up, and attack before pressure arrives.
3. **Ball Hunter** — stop following the crowd and find a chance to win the ball.
4. **Find the Way Forward** — find open space or make a useful forward pass rather than automatically retreating.
5. **Fast Forward** — decide quickly: pass, dribble into space, or shoot when close enough.

Each mission has a decision question, interactive playable field, and a child-friendly **winning-moment screenshot** with the player's location circled, plus a physical drill.

## How to play

1. Tap **Start Quick Practice** or pick a mission.
2. Choose what you should do in the match scenario (or skip to the field).
3. On the field, tap or drag where the blue **8 / YOU** player should run.
4. Get close to the ball and tap **STEAL**, or **PASS** to a forward teammate, or **SHOOT** when close to the other goal.
5. After success, look at the field snapshot and discuss why the move worked. Repeat with a real soccer ball.

**Desktop controls:** Arrow keys or WASD move; Space steals, J passes, K shoots.

**Parents:** Keep sessions short (~5–10 minutes). Encourage confidence and effort, not risky tackles. Soccer decisions are contextual; passing backward is sometimes correct, and aggressive play should never mean pushing or colliding.

## Technology

- **Vanilla HTML, CSS, JavaScript, and Canvas** (no build, backend, AI inference, or external libraries)
- Designed for touchscreen phones and tablets, also playable on desktop
- `localStorage` keeps stars locally; canvas snapshots only live in current browser memory
- Browser-based voice coaching is optional, where the browser supports speech synthesis
- The HTML file itself can be opened offline; browser caches of the hosted site may vary

## Run, stop, debug

- **Run locally:** open `index.html` in your browser, or `python3 -m http.server 8000` then visit http://localhost:8000/.
- **Stop server:** Ctrl+C in the terminal.
- **Troubleshoot:** enable browser Developer Tools → Console; for audio, tap once to unlock audio on mobile; use a recent Chrome/Safari/Firefox.
- **Persistence:** stars are saved only in that browser's local storage under `soccer-quest-progress`.
- **Network:** no API calls, tracking, remote storage, or user sign-in.

## Deployment (GitHub Pages)

The repository contains `.github/workflows/pages.yml`. It publishes the root static site whenever the default branch (`main`) changes.

1. Verify your GitHub plan permits Pages for the repository's visibility. GitHub Free organizations require a **public** repository for Pages.
2. In the GitHub repository, open **Settings → Pages** and choose **GitHub Actions** as the build/deployment source. Enable GitHub Pages if prompted.
3. Check **Actions → Deploy Soccer Quest to GitHub Pages** for a successful run. If the workflow was added before Pages was enabled, run it manually from the Actions tab.
4. Visit https://chandus-garage.github.io/soccer-game/ once GitHub reports deployment complete.

> Important: The repository was private when this game was first prepared. Making it public changes who can read the source files. Do that only if you intend it.

## Development

`index.html` is the single source of truth for the app. `plan.md` contains requirements, current status, next iterations, and test criteria.

### Smoke tests

- Start all five missions and complete each once.
- Each success screen shows an accurate, readable snapshot with your blue player circled.
- Repeat mission and return home; saved star progress persists after reload.
- Test at 390 × 844 mobile portrait and desktop landscape dimensions.
- Verify gameplay with sound/voice off, keyboard, and touch controls.

## License

No license selected yet. Repository owner should select one before accepting outside contributions or public reuse.