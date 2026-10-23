# Lera's Workouts

A simple workout tracker for iPhone. It's a web app you add to the Home Screen. It has no server and no login, and all data stays on the phone (in `localStorage`).

## Features
- 4 exercises (you can add more), each with separate **Isometric** and **Dynamic** progressions
- Weight (kg/lbs), sets, reps or hold time, and the machine setting (IN / OUT)
- **Done** tick logs the session for the selected day. Untick to undo.
- **Times done** is worked out per day: how many sessions in a row used the exact same weight, unit, sets, reps/time and machine setting. Changing any of them starts again at ×1; earlier days keep their own setup and count
- Feel score from 1 (easy) to 5 (hard), saved for each day's session
- Aims kept as free text
- Progress graph of weight, or reps/time, over time, plus an editable history
- Opens on a start page with two sections: **Knee & legs** and **Arms**
- Arms **Today**: step between days with ‹ › or tap the date for a calendar, so any past day can be logged
- **Guitar**, logged in minutes (usual minutes prefilled when ticked)
- Arms **Progress** tab: stats, a **Points per day** chart stacked by exercise (week to all time), a day-by-day log, body weight setting and backup
  - Load = weight lifted (kg) × sets × reps; holds count 1 rep per 3 s; assisted exercises use body weight minus the assist
  - Points = load ÷ the first logged session of that exercise and type × 100; guitar is 50 points per 30 min
- Each exercise's chart can also show **Volume** (load) and **Est. max** (weight × (1 + reps ÷ 30))
- 5-week cycle tracker (Dynamic / ISO / Dynamic / ISO / Deload)
- Export/Import of a JSON backup

## Knee progress
A separate section in `knee/`, opened from the **Knee** card on the home screen (or directly at `…/knee/`):
- Daily knee pain on an absolute scale from 0 (no pain) to 50 (can't do anything or bear weight), with described markers every 10 points (shown under the slider and in a tappable scale guide)
- Daily exercise checklist: each exercise has default sets × reps (set via ⚙︎) that are prefilled when ticked; each day stores its own sets, reps and easiness (1–5), so changing the defaults later doesn't alter past days
- Medicine timeline: courses with name, dose, start and stop dates; each day shows what you're taking (e.g. Naproxen · day 8)
- Ice: times iced per day for each knee (left / right)
- Steps and a free-text note for each day
- Tap the date to pick a day from a calendar (logged days are dotted, coloured by pain)
- Goals list, where you mark the day each goal is realised
- Progress charts (pain 0–50, steps, exercise reps per day stacked by exercise, and a pain-vs-activity view with a same-day / next-day pain comparison) over a week, 2 weeks, a month, 3 months or all time, plus a day-by-day log
- Its own Export/Import backup, separate from the workouts one

## Put it on the iPhone
The app has to be served over HTTPS so it can install and work offline. GitHub Pages is free:
1. Push this folder to a GitHub repo.
2. Repo → Settings → Pages → Deploy from branch → `main` / root.
3. On the iPhone, open the Pages URL in **Safari** → Share → **Add to Home Screen**.

Always open it from the Home Screen icon. Safari and the Home Screen app keep separate data.

## Updating
After changing files, bump `CACHE` in `sw.js` (for example `workouts-v2`) so phones pick up the new version. The knee section has its own `knee/sw.js` with a separate `CACHE` (`knee-v8`).
