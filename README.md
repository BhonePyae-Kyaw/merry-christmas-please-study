# AZ Dash

A Subway Surfers–style endless runner for studying the **AWS Certified Solutions Architect – Associate (SAA-C03)** exam.

A question rolls in, then three gates come toward you — one per lane (`1a`, `1b`, `1c`). Switch lanes and run through the gate with the right answer. Jump the yellow **503** hurdles and dodge the red **429 THROTTLED** blocks.

## Play

It's a single static file with no build step. Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Features

- 70 scenario questions across the four SAA-C03 domains: Security (30%), Resilience (26%), Performance (24%), Cost (20%)
- Each gate shows the correct answer plus 2 of 3 distractors, picked at random
- **Runner** mode (3 lives, obstacles) or **Study** mode (no obstacles, no lives)
- Three reading speeds: Chill, Normal, Exam day
- Streak multiplier up to ×5
- Explanation after every answer; a review list of missed questions at the end of each run
- Best score and per-domain accuracy saved in `localStorage`

## Controls

| Action | Keyboard | Phone |
| --- | --- | --- |
| Switch lane | `←` `→` / `A` `D` / `1` `2` `3` | Swipe or tap left/right side |
| Jump | `↑` / `Space` / `W` | Swipe up or tap center |
| Drop fast | `↓` / `S` | Swipe down |
| Pause | `P` / `Esc` | Pause button |

## Adding questions

Questions live in the `QUESTIONS` array near the top of the `<script>` in `index.html`:

```js
{d:"sec", q:"Scenario text?", a:"Correct answer", w:["Wrong 1","Wrong 2","Wrong 3"], e:"Why the answer is right."}
```

`d` is one of `sec`, `res`, `perf`, `cost`. Keep answers short (about 30 characters) so they fit on the gates.

## Disclaimer

Unofficial practice questions written for study. Not affiliated with or endorsed by AWS.
