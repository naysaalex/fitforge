# FitForge

An AI-powered personal health and fitness web app. Generates personalized 2-week workout and meal plans, adapts to your menstrual cycle, and saves everything to your account in the cloud.

---

## What it does

- **AI-generated 2-week plans** — personalized workouts and daily meals based on your metrics, goals, and meal prep preferences
- **Cycle syncing** — automatically calculates your menstrual phase day-by-day across the full 14-day plan and adapts workouts and nutrition accordingly
- **Calendar & list view** — toggle between a 14-day calendar grid and a scrollable list; tap any day to expand workouts and meals
- **Recipe links** — every meal links to an AllRecipes search
- **Biweekly check-in** — update your metrics, correct your cycle phase if needed, and regenerate a fresh plan
- **Cloud storage** — all data saved to Firebase; persists across devices and browser refreshes
- **Per-user accounts** — each user signs in with their own email/password and provides their own Claude API key

---

## Tech stack

| Layer | Tool |
|---|---|
| Hosting | GitHub Pages (free) |
| Auth & database | Firebase Authentication + Cloud Firestore |
| AI plan generation | Anthropic Claude API (`claude-sonnet-4-5`) |
| Recipe links | AllRecipes search |
| Frontend | Vanilla HTML / CSS / JS — no frameworks |

---

## First use

1. Create an account in the app
2. Tap **⚙ API Key** → enter your Anthropic Claude API key (from [console.anthropic.com](https://console.anthropic.com))
3. Fill in **Profile** — metrics, cycle tracking if applicable
4. Fill in **Goals** — targets, training setup, meal prep preferences
5. Tap **Generate my 2-week plan**

---

## Menstrual cycle syncing

When cycle tracking is enabled, the app calculates the exact phase for each of the 14 days using your last period date and cycle length — including mid-plan phase transitions.

| Phase | Days | Workout | Nutrition |
|---|---|---|---|
| 🔴 Menstrual | 1–5 | Yoga, walking, mobility only | Iron, magnesium, anti-inflammatory |
| 🔵 Follicular | 6–13 | Progressive overload | Complex carbs, cruciferous veg |
| 🟢 Ovulatory | 14–16 | Heavy compounds, HIIT | High protein, zinc, antioxidants |
| 🟡 Luteal | 17–28 | Moderate, steady-state | Magnesium, B6, complex carbs, +150 kcal |

At check-in, the app shows your auto-calculated current phase with a correction toggle if the timing is off. Corrections update your period date permanently for future plans.

---

## RingConn + Apple Health

RingConn syncs to Apple Health. At each 2-week check-in, pull your metrics from the Health app:

| Metric | Location |
|---|---|
| Weight | Browse → Body Measurements → Weight |
| Body Fat % | Browse → Body Measurements → Body Fat % |
| Resting HR | Browse → Heart → Resting Heart Rate |
| HRV | Browse → Heart → Heart Rate Variability |
| SpO2 | Browse → Respiratory → Blood Oxygen |
| Sleep | Browse → Sleep → Sleep Duration |

---

## Cost

| Item | Cost |
|---|---|
| GitHub Pages | Free |
| Firebase Spark plan | Free |
| Claude API | ~$0.05–0.15 per plan generation |

A $5 Anthropic credit covers roughly 50–250 plan generations. Each user pays only for their own usage via their own API key.

---

## Privacy

- Users can only read and write their own Firestore data (enforced by security rules)
- Firebase API key is restricted to your GitHub Pages domain
- Claude API keys are stored in each user's private Firestore document
- No analytics or tracking
