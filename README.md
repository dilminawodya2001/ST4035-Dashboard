# ST4035 — Binary Logistic Regression Dashboard

An interactive, single-file HTML dashboard for exploring core concepts in Binary Logistic Regression — built for the ST4035 module. It runs entirely in the browser with no server, no build step, and no dependencies to install.

---

## Live Demo

Open `s16629.html` directly in any modern browser — that's all you need.

---

## Features

| Panel | What it shows |
|---|---|
| **Class Distribution** | Before/after class counts for the chosen balancing strategy |
| **Link Functions** | Side-by-side comparison of Logit, Probit, and Complementary log-log curves; the active link is highlighted |
| **ROC Curve** | Receiver Operating Characteristic curve with AUC score, regenerated on every parameter change |
| **Confusion Matrix** | Colour-coded 2 × 2 heatmap showing TP / FN / FP / TN as percentages and raw counts |
| **Summary Footer** | Live readout of AUC, Accuracy, Sensitivity, Specificity, active link function, and balancing method |

### Sidebar Controls

- **Sample size** slider — adjusts the simulated dataset size (n)
- **Class imbalance** slider — sets the minority-class proportion
- **Balancing strategy** — toggle between None, Oversampling, Undersampling, and SMOTE
- **Link function** — toggle between Logit, Probit, and Complementary log-log

All charts and metrics update in real time as controls change.

---

## Project Structure

```
.
└── s16629.html   # Complete self-contained dashboard (HTML + CSS + JS)
```

Everything — markup, styles, and JavaScript — lives in one file for easy sharing and deployment.

---

## Technologies Used

- **Chart.js 4.4.1** — bar charts, line charts, and the ROC curve (loaded from cdnjs)
- **Vanilla JavaScript** — simulation logic, confusion matrix heatmap drawn on Canvas
- **CSS custom properties** — dark navy theme with a consistent design system
- **Google Fonts** — Nunito (UI) and Fira Code (monospace values)

No frameworks, no build tools, no runtime dependencies beyond a browser.

---

## Getting Started

### View locally

```bash
# Clone the repo
git clone https://github.com/<your-username>/<repo-name>.git

# Open the dashboard
open s16629.html          # macOS
start s16629.html         # Windows
xdg-open s16629.html      # Linux
```

Or just double-click the file in your file manager.

### Deploy to GitHub Pages

1. Push the file to your repository.
2. Go to **Settings → Pages**.
3. Set the source to the branch and folder containing `s16629.html`.
4. GitHub Pages will serve it at `https://<your-username>.github.io/<repo-name>/s16629.html`.

---

## How the Simulation Works

The dashboard generates a synthetic binary classification dataset based on the selected parameters:

1. **Data generation** — `n` observations are drawn with class probabilities determined by the imbalance slider.
2. **Balancing** — the chosen strategy (oversampling, undersampling, or SMOTE-like resampling) adjusts the class counts.
3. **Probability estimation** — predicted probabilities are computed using the selected link function (Logit / Probit / C-log-log).
4. **Threshold sweep** — the ROC curve and AUC are derived by sweeping the classification threshold from 0 to 1.
5. **Confusion matrix** — computed at the 0.5 default threshold and displayed as a normalised heatmap.

---

## Module Context

This dashboard was created as part of **ST4035 — Statistical Modelling**, covering:

- Binary Logistic Regression
- Link functions (Logit, Probit, Complementary log-log)
- Class imbalance and resampling strategies
- Model evaluation: ROC/AUC, confusion matrix, sensitivity, specificity

---

## License

This project is released for educational use. Feel free to fork, adapt, and share.
