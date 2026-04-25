[README.md](https://github.com/user-attachments/files/27088787/README.md)
# FitForge — AI-Powered Personal Health & Fitness System

A mobile-first web app that generates personalized 2-week workout and meal plans using AI, with built-in support for menstrual cycle syncing via RingConn and Apple Health.

---

## Features

- **AI-generated 2-week plans** — personalized workout splits and daily meal suggestions based on your current metrics and goals
- **Menstrual cycle syncing** — workouts and nutrition adapt day-by-day across all 4 phases (menstrual, follicular, ovulatory, luteal)
- **RingConn + Apple Health integration** — step-by-step guide to pull your latest biometrics (HRV, resting heart rate, SpO2, sleep, body fat) directly from Apple Health at each check-in
- **Biweekly check-in system** — update your metrics every 2 weeks and get a refreshed, progressively harder plan
- **Blood panel awareness** — input cholesterol, HDL, LDL, triglycerides, and HbA1c for a more tailored health assessment
- **Saves your data locally** — your profile, goals, and API key are stored in your browser so you never have to re-enter them
- **Works as a home screen app** — add to your iPhone or Android home screen for a native app-like experience

---

## Live Demo

> `https://yourusername.github.io/fitforge`
> *(replace `yourusername` with your GitHub username)*

---

## Setup

### 1. Get an Anthropic API Key

This app uses the Claude API to generate your plans.

1. Go to [console.anthropic.com](https://console.anthropic.com) and create an account
2. Click **API Keys** in the left sidebar
3. Click **Create Key**, name it anything, and copy it
4. Open the app, tap **⚙ API Key** in the top right, paste your key, and save

Your key is stored only in your browser's local storage — it never leaves your device.

### 2. Deploy to GitHub Pages

1. Upload `index.html` to this repository (drag and drop via GitHub's web UI)
2. Go to **Settings → Pages**
3. Under **Branch**, select `main` and folder `/ (root)`, then click **Save**
4. Wait ~60 seconds — your site will be live at `https://yourusername.github.io/fitforge`

### 3. Add to your phone home screen

**iPhone (Safari only):**
1. Open your GitHub Pages URL in Safari
2. Tap the **Share** button (box with arrow)
3. Scroll down and tap **Add to Home Screen**
4. Name it FitForge and tap **Add**

**Android (Chrome):**
1. Open your GitHub Pages URL in Chrome
2. Tap the three-dot menu
3. Tap **Add to Home screen**

---

## How to Use

### First time
1. **Profile tab** — enter your name, age, sex, height, and current metrics (weight, BMI, body fat %, waist). Blood panel values are optional but improve plan accuracy.
2. **Cycle tracking** (women only) — toggle on menstrual cycle tracking, enter your cycle length, last period start date, and current phase.
3. **Goals tab** — set your target metrics, primary fitness goal, fitness level, gym days per week, equipment access, and any dietary preferences or injuries.
4. Tap **Generate my 2-week plan** — your personalized plan appears in the Plan tab.

### Every 2 weeks (Check-In tab)
1. Open Apple Health on your iPhone and screenshot your summary
2. Fill in your updated metrics (weight, HRV, resting HR, SpO2, sleep, body fat)
3. Rate how the last 2 weeks went (energy, workout completion, diet adherence)
4. Tap **Get my refreshed plan** — the AI adjusts intensity and variety based on your progress and biometrics

---

## Menstrual Cycle Syncing

When cycle tracking is enabled, every day of your 2-week plan is adapted to your current cycle phase:

| Phase | Days | Training | Nutrition focus |
|---|---|---|---|
| 🔴 Menstrual | 1–5 | Low intensity — yoga, walking, mobility | Iron-rich foods, anti-inflammatory, magnesium |
| 🔵 Follicular | 6–13 | Rising intensity — progressive overload, new movements | Complex carbs, cruciferous vegetables, lean protein |
| 🟢 Ovulatory | 14–16 | Peak performance — heavy compounds, HIIT | High protein, zinc-rich foods, antioxidants |
| 🟡 Luteal | 17–28 | Moderate — steady-state cardio, lighter strength | Complex carbs, magnesium, B6, slightly higher calories |

Your RingConn ring tracks your cycle via skin temperature and heart rate data and syncs this to Apple Health. At each check-in, you can update your current phase so the next plan reflects where you are in your cycle.

---

## RingConn + Apple Health: Where to Find Each Metric

| Metric | Path in Apple Health |
|---|---|
| Weight | Browse → Body Measurements → Weight |
| Body Fat % | Browse → Body Measurements → Body Fat Percentage |
| Resting Heart Rate | Browse → Heart → Resting Heart Rate |
| HRV | Browse → Heart → Heart Rate Variability |
| Blood Oxygen (SpO2) | Browse → Respiratory → Blood Oxygen |
| Average Sleep | Browse → Sleep → Sleep Duration |
| Cycle Phase | Browse → Cycle Tracking — or check the RingConn app directly |
| Waist circumference | Measure manually with a tape measure (not tracked in Apple Health) |

**Pro tip:** Take a screenshot of your Apple Health Summary screen before opening the app — all your key numbers are visible in one place.

---

## Metrics Tracked

**Core (entered manually or from Apple Health):**
- Weight, BMI, body fat %, waist circumference

**Biometrics from RingConn via Apple Health:**
- Resting heart rate, HRV, SpO2, average sleep duration

**Optional blood panel:**
- Total cholesterol, HDL, LDL, triglycerides, HbA1c

**Cycle data (women):**
- Cycle length, last period start date, current phase

---

## Privacy

- **No account required** — the app runs entirely in your browser
- **No server** — there is no backend; all data stays on your device
- **API key stored locally** — your Anthropic key is saved in your browser's `localStorage` and is never transmitted anywhere except directly to Anthropic's API
- **No tracking or analytics** — this app collects zero data about you

---

## Updating the App

When a new version of `index.html` is available:

1. Go to your `fitforge` repository on GitHub
2. Click on `index.html`
3. Click the pencil (edit) icon, or use **Add file → Upload files** to replace it
4. Commit the change — GitHub Pages will update your live site within ~60 seconds

Your saved profile, goals, and API key will persist across updates since they're stored in your browser.

---

## Tech Stack

- **Vanilla HTML/CSS/JavaScript** — no frameworks, no build step, no dependencies
- **Anthropic Claude API** (`claude-sonnet-4-20250514`) — plan generation
- **Browser localStorage** — profile and settings persistence
- **GitHub Pages** — free static site hosting

---

## Roadmap / Future Ideas

- [ ] Native iOS app for direct Apple Health API access (automatic data sync)
- [ ] Export plan as PDF
- [ ] Progress charts over time
- [ ] Barcode scanning for meal logging
- [ ] Integration with MyFitnessPal or Cronometer

---

## License

Personal use. Built with [Claude](https://claude.ai) by Anthropic.
