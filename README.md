# ☕ Coffee LCA Expert (Simulator)

![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-live-blue)

**An interactive serious game about the Life Cycle Assessment (LCA) of coffee consumption.**

Experience the environmental impact of your daily cup of coffee. This simulator guides users through the entire lifecycle—from cultivation in the tropics to disposal in your kitchen—based on real scientific data.

🔗 **[Play the Live Demo](https://mclovin55c.github.io/kaffee_lca/)**

---

## 🎯 About the Project

This web-based tool was designed to educate consumers about the hidden CO₂ costs of different coffee preparation methods. Unlike simple calculators, it uses a **gamified approach**:

1.  **Sorting Phase:** Learn which process belongs to which lifecycle stage.
2.  **Estimation Phase:** Guess the impact distribution yourself.
3.  **Analysis Phase:** Compare your intuition with scientific reality.
4.  **Simulation Phase:** Experiment with variables like electricity mix, recycling behavior, or machine efficiency to lower the footprint.

### Supported Systems
* **Instant Coffee** (Spray-dried soluble)
* **Filter Coffee** (Drip filter)
* **Capsule Coffee** (Single-serve aluminum)

---

## 🔬 Scientific Basis

The data and logic are based on the peer-reviewed study:

> **Humbert, S. et al. (2009).** *Life cycle assessment of spray dried soluble coffee and comparison with alternatives (drip filter and capsule espresso).* Journal of Cleaner Production.

**Key Concepts Implemented:**
* **System Boundaries:** Cradle-to-Grave (Cultivation, Production, Use, End-of-Life).
* **Functional Unit:** One cup of coffee (normalized to specific ml/caffeine content).
* **End-of-Life Credits:** Implementation of negative emission values (bonuses) for recycling or waste-to-energy recovery.
* **Regional Electricity:** Simulation of different energy grids (EU, DE, FR, NO) affecting the Use Phase.

---

## 🛠️ Tech Stack

This project is a **Single Page Application (SPA)** built with Vanilla Technologies. No build step or package manager (npm/yarn) is required.

* **HTML5 / CSS3:** Responsive Grid-Layout & CSS Variables for theming.
* **JavaScript (ES6+):** Modular logic for game state and internationalization.
* **[Chart.js](https://www.chartjs.org/):** Real-time visualization of CO₂ data.
* **[SortableJS](https://sortablejs.github.io/Sortable/):** Drag & Drop functionality.
* **[Lucide Icons](https://lucide.dev/):** Lightweight UI icons.

---


### Modifying Scientific Data
To update the underlying LCA data (e.g., for a new study), locate the `const DATA` object:

```javascript
const DATA = {
    Instant: { 
        values: [14, 4, ...], // Percentage distribution
        abs: 74,              // Absolute CO2e in grams
        afterlife: -2         // Bonus/Malus points
    },
    // ...
};
