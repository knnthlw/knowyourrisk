# KnowYourRisk ⚖️

> Understand the real legal consequences you could face — by state, charge, and situation.

A free, open-source legal consequence calculator. Clean UI, zero dependencies, works on any device.

**[Live Demo →](https://knnthlw.github.io/knowyourrisk/)**

---

## What it covers

6 violation categories across all 50 US states:

| Category | Sub-types |
|---|---|
| 🚗 Speeding | Standard road, school zone, construction zone, highway — live fine calculator |
| 🍺 DUI / DWI | First offense, second offense, felony DUI |
| 💊 Drug offenses | Marijuana possession, hard drug possession, distribution, paraphernalia |
| 📦 Theft | Petty theft, grand theft, robbery |
| 🥊 Assault | Simple, domestic, aggravated |
| 🔫 Weapon offenses | Unlawful carry, brandishing, felon in possession |

Results include fine range, jail/prison estimate, felony vs. misdemeanor classification, and state-specific notes.

---

## Deploy on GitHub Pages (3 steps)

1. Fork this repo
2. Go to **Settings → Pages → Source → main / root**
3. Visit `https://knnthlw.github.io/knowyourrisk/`

No build step. No npm install. No dependencies.

---

## Run locally

```bash
open index.html
# or
python3 -m http.server 8080
```

---

## Customizing penalty data

All data lives in the `PENALTIES` and `STATE_MODS` objects inside `index.html`.

**Add or adjust a state modifier:**

```js
const STATE_MODS = {
  "California": { mult: 1.8, note: "CA has some of the highest base fines in the country" },
  // Add yours:
  "Your State":  { mult: 1.3, note: "Optional note shown in results" },
};
```

`mult: 1.0` = national average baseline. `1.5` = 50% higher fines.

**Add a new sub-type to an existing category:**

```js
PENALTIES.theft.carjacking = {
  label: "Carjacking",
  fine: [5000, 25000],
  jail: [730, 5475],    // days
  felony: true,
  notes: "Violent felony; federal charges possible if crossing state lines"
};
```

---

## Roadmap

- [ ] Prior criminal record toggle (affects sentencing tier)
- [ ] Marijuana legalization flag auto-detected per state
- [ ] Share results as link
- [ ] Attorney finder integration
- [ ] PWA / installable app
- [ ] Spanish language support

---

## Legal disclaimer

KnowYourRisk provides general educational estimates based on typical statutory ranges. Actual outcomes vary based on prior record, judge discretion, plea agreements, and local court practices. **This is not legal advice.** Users should consult a licensed attorney for their specific situation.

---

## License

MIT — free to use, modify, and distribute.
