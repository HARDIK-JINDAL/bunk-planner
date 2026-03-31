# bunk.planner

> **skip smart, not random** — an attendance optimizer for students

A single-file web app that figures out the **maximum number of classes you can skip** while keeping every subject above its minimum attendance requirement. No backend, no signup, no tracking. Just open and use.

🔗 **[Live Demo](https://HARDIK-JINDAL.github.io/bunk-planner)** 

---

## what it does

Most students guess which days to bunk. This tool runs a greedy optimization algorithm across your full timetable and tells you *exactly* which days are safe to skip — and which ones you absolutely cannot miss.

**Input:**
- Your subjects, current attendance counts, and minimum % required
- Your timetable (how many hours each subject has on each day order)
- Your college's day order calendar for the month (with holidays)

**Output:**
- Maximum skippable days while staying ≥ minimum attendance in all subjects
- A color-coded calendar: green = skip safely, red = must attend, amber = risky
- Per-subject projected % and buffer after the optimal plan

---

## how to use

The app walks you through 5 steps:

| Step | What you do |
|------|-------------|
| **01 subjects** | Add each subject with total classes held and classes attended so far |
| **02 timetable** | Enter how many hours each subject has on each day order (D1–D5) |
| **03 day order** | Set the starting day order for the 1st of the month, mark holidays, hit auto-fill |
| **04 attendance** | Optionally mark days you already know you're attending |
| **05 results** | See the optimal bunk plan with a full calendar breakdown |

---

## the algorithm

The optimizer uses a **greedy approach**:

1. Start by assuming you attend *all* working days
2. Score each day by total class hours across all subjects (fewer hours = cheaper to skip)
3. Sort days cheapest-first, then greedily try removing each one
4. A day gets marked as **safe to skip** only if every subject still meets its minimum % after skipping it
5. Repeat until no more days can be removed

This guarantees the **maximum number of skips** possible without violating any attendance constraint.

---

## features

- ✦ Greedy skip optimizer — mathematically maximum safe bunks
- 📅 Auto-fill day order calendar from a starting order + holidays
- 🎨 Color-coded results calendar (skip / attend / risky / must go)
- 📊 Per-subject projected % and buffer above minimum
- 🔒 100% client-side — no data ever leaves your browser
- 📱 Mobile-friendly
- 0️⃣ Zero dependencies, zero accounts, zero ads

---

## run locally

Just open the file — no build step, no server needed:

```bash
git clone https://github.com/HARDIK-JINDAL/bunk-planner
cd bunk-planner
open index.html
```

Or just double-click `index.html`.

---

## tech

Pure HTML + CSS + vanilla JavaScript. Single file, ~800 lines, no frameworks, no build tools.

---

## license

MIT — do whatever you want with it.
