# Soccer Quest — Product & Delivery Plan

Updated: 2026-10-10

## 1. Mission and audience

Teach soccer decision-making to a child around age eight through *short, interactive scenarios* that translate to better game-day habits. The goal is assertive, safe play—not reckless tackling, over-dribbling, or automatic running toward every crowd.

### Specific behaviors to improve

- **Ball watching:** standing or running parallel to groups chasing the ball without trying to intercept, challenge, or move into helpful space.
- **Retreating under pressure:** turning or dribbling toward the team's own goal by default instead of scanning for useful forward routes and teammates.
- **Passive defending:** backing away continuously without reducing the attacker's space.
- **Slow restarts:** unnecessary tricks or hesitation when a forward teammate is available.
- **Slow first action after possession:** waiting so long that defenders recover and steal.

### Three memorable cues

**WIN IT** (be brave and challenge safely) → **LOOK UP** (find space or a teammate) → **GO** (move or pass quickly).

## 2. Product principles

- Ages ~7–9; simple language, bright visuals, instant replay and positive feedback.
- 5–10 minute sessions. Practice transfer through short backyard drills.
- Real decisions are contextual: backward passes and containing a dangerous attacker can be correct; don't teach blanket rules or physical aggression.
- Low/no cost, privacy-preserving, no account, no ads, no backend in MVP.
- Touch-first; desktop keyboard fallback; optional audio and voice.

## 3. MVP delivered

| Feature | Status | Notes |
|---|---|---|
| Responsive mobile and desktop interface | Complete | Single `index.html`, no libraries |
| Five core missions | Complete | Brave Defender, Win It & Go, Ball Hunter, Find the Way Forward, Fast Forward |
| Scenario decision questions and coaching | Complete | Correct/incorrect explanations |
| Touch playable 2D soccer field | Complete | Drag/tap movement; dynamic red defenders |
| Steal, pass, shoot actions | Complete | Simple deterministic rules; not full physics |
| Timer, progress stars and repeat | Complete | Stars stored in browser local storage |
| Optional voice coach and game sounds | Complete | Browser-dependent |
| Real ball practice drills | Complete | One per mission |
| **Winning-moment screenshot** | **Complete** | Captured on success from live Canvas state; highlights blue player, includes message and forward-pass indicator if relevant; shown on result screen; stays in memory only |
| GitHub Pages deployment workflow | Ready | Requires Pages enabled, plus a Pages-eligible repo/plan |

## 4. Roadmap

### P0 — Before next game (complete)

- [x] Provide five mission lessons built around observed mistakes.
- [x] Enable real gameplay with controls and simple moving defenders.
- [x] Show what went right on the success screen with a snapshot of *actual gameplay* (not a generic illustration).
- [x] Add real-world parent drills and simple coaching cues.
- [x] Prepare repository source and GitHub Pages workflow.
- [ ] **Owner action:** Enable Pages under Settings → Pages and ensure repo visibility/plan supports Pages; verify public URL.

### P1 — Better learning transfer (next)

- [ ] Add **before/after replay** showing the starting position, movement trail, and finish position, with animated arrows for the good decision.
- [ ] Show **successful and unsuccessful paths side by side**; avoid shaming and give retry guidance.
- [ ] Add a short **two-second decision clock** to practice faster recognition, separate from movement time.
- [ ] Make defender AI obey real soccer constraints (distance, angles, momentum), including a defensive stance vs. rushing too far.
- [ ] Reward a **smart intercept or pressing angle**, not just any close-range button press.
- [ ] Track decision quality by mission, not only completion speed; show confidence and improvement rather than ranking kids.
- [ ] Test with the child and revise awkward controls/wording.

### P2 — Scenarios & skill progression

- [ ] Parent scenario builder: drag players, ball, goals and teammates onto the pitch; set goal direction and choose defensive reaction.
- [ ] More situations: 1v1, 2v1, overloads, breakaways, passing lanes, recovering after a turnover.
- [ ] Difficulty levels: no time pressure → moving defenders → varying speeds and positions → match-like small-sided play.
- [ ] Show recommended decision **and why alternatives also sometimes make sense**.
- [ ] Introduce calm first touch, body positioning, changing direction without panic, passing to wide space.
- [ ] Add replay saved locally per mission (privacy-first; opt-in).

### P3 — Distribution and polish

- [ ] Installable PWA (`manifest.webmanifest`, icons, service worker with offline cache after initial visit).
- [ ] Full accessibility audit: reduced motion, large targets, narration, colorblind labeling, contrast and captions.
- [ ] Separate the single HTML into modules if the codebase grows (Vite + React/TypeScript or Phaser only if justified by complex gameplay).
- [ ] Add automated browser regression tests (Playwright) for all mission results, snapshot capture and touch behavior.
- [ ] Optional local-only parent dashboard (progress and practice focus).
- [ ] Review license, privacy policy and contributions guide before opening project to outside contributors.

### Future / optional, not MVP

- [ ] Adaptive challenges based on frequent wrong decisions, without an LLM.
- [ ] Voice-guided parent-and-child drills; multilingual cues.
- [ ] User-supplied match scenarios or clips, with explicit privacy controls and consent.
- [ ] Cloud sync or accounts only if multi-device requirements justify them.

## 5. Data flow & architecture

```text
Child selects mission
  → answer scenario (feedback)
  → play Canvas field (player + opponent rules)
  → win/loss decision
  → [success] render final state → canvas screenshot + highlight
  → results page (image + takeaway + real-world drill)
  → stars saved to device localStorage
```

Everything is client-side. **No personal identifiers, pictures of children, cloud inference, or network API requests.** Winning screenshots are generated inside the browser and shown immediately. They are not stored or uploaded.

## 6. Quality acceptance tests

- [x] Desktop/mobile browser smoke test: all five missions can be completed without JavaScript errors.
- [x] Mission complete shows real screenshot, player visibly highlighted, and what-to-remember guidance.
- [ ] Test on actual child device/browser with touch gestures (especially small iPhone/Android screens).
- [ ] Test accessibility using VoiceOver/TalkBack.
- [ ] Validate GitHub Pages deployment after Pages settings have been enabled.

## 7. Feedback questions for parent after first practice

1. Does he understand that the player labeled **YOU** is his player?
2. Can he move the player on his own with touch controls?
3. Does the winning-moment image help him explain *why* he succeeded?
4. Which mission is most fun? Which confuses him?
5. Does he try one practiced behavior in the next real game?

Keep development lightweight until actual playtime validates the approach.