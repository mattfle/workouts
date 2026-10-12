# Lera's Workouts

A simple workout tracker for iPhone. It's a web app you add to the Home Screen. It has no server and no login, and all data stays on the phone (in `localStorage`).

## Features
- 4 exercises (you can add more), each with separate **Isometric** and **Dynamic** progressions
- Weight (kg/lbs), sets, reps or hold time, and the machine setting (OUT / IN / plugged in…)
- **Done today** tick: adds 1 to "times done" and logs the session. Untick to undo.
- Changing the weight, unit, sets or reps/time counts as a new configuration and resets "times done"
- Feel score from 1 (easy) to 5 (hard)
- Aims kept as free text
- Progress graph of weight, or reps/time, over time, plus an editable history
- 5-week cycle tracker (Dynamic / ISO / Dynamic / ISO / Deload)
- Export/Import of a JSON backup

## Knee progress
A separate section in `knee/`, opened from the **Knee** card on the home screen (or directly at `…/knee/`):
- Daily knee pain compared to yesterday (better / same / worse, ±1–10), giving a running total where lower means less pain
- Steps and a free-text note for each day
- Goals list, where you mark the day each goal is realised
- Progress charts (pain total and steps) over 2 weeks, a month, 3 months or all time, plus a day-by-day log
- Its own Export/Import backup, separate from the workouts one

## Put it on the iPhone
The app has to be served over HTTPS so it can install and work offline. GitHub Pages is free:
1. Push this folder to a GitHub repo.
2. Repo → Settings → Pages → Deploy from branch → `main` / root.
3. On the iPhone, open the Pages URL in **Safari** → Share → **Add to Home Screen**.

Always open it from the Home Screen icon. Safari and the Home Screen app keep separate data.

## Updating
After changing files, bump `CACHE` in `sw.js` (for example `workouts-v2`) so phones pick up the new version. The knee section has its own `knee/sw.js` with a separate `CACHE` (`knee-v1`).
