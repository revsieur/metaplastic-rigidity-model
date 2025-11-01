# A Minimal Mechanistic Model of Emergent Pathological Rigidity

This repository contains the full code (`.ipynb`), final paper (`.pdf`), and figures for a computational psychiatry project modeling pathological rigidity.

The central finding is that rigidity can emerge as a **stable, suboptimal "pathological equilibrium"** (a state of "incomplete unlearning") rather than as a complete failure of the learning system.

---

## 🔬 Core Hypothesis & Model

We model rigidity as a "tug-of-war" between two learning systems, inspired by opponent-process theories in neuroscience:

1.  **A "Fast" System (Dopamine-like):** A standard, RPE-driven Q-learner.
2.  **A "Slow" System ($S_{meta}$):** A novel metaplastic variable that abstracts two biological functions:
    * **Serotonin-like Function:** It *only* integrates negative RPEs (a "punishment tracker").
    * **Astrocyte-like Timescale:** It integrates these signals slowly, creating a persistent "aversive mood."

This "mood" signal ($\Delta Q_{slow}$) actively opposes the "reality" signal ($\Delta Q_{fast}$), resulting in a "stuck" belief.

## 📈 Key Findings

1.  **Pathological Equilibrium:** The Metaplastic Agent doesn't just "slow down"; it settles at a stable, suboptimal behavior (continuing to choose the bad arm ~34% of the time) because its internal "mood" signal almost perfectly cancels the "reality" signal.
2.  **Quantitative Proof:** The pathological agent's unlearning rate is **10.6x slower** than the healthy agent's.
3.  **Causality:** An "ablation" therapy that sets the "mood" signal's strength to 0 is the *only* intervention that "cures" the agent, proving the $S_{meta}$ pathway is the causal variable.

## 🗂 Repository Structure

* `newproj.ipynb`: The complete Jupyter Notebook containing all 15 cells of code to run the experiments from scratch.
* `newproj.pdf`: The final, complete research paper describing the model, results, and discussion.
* `/figures`: (Recommended) You can put all your `.png` files (`1a.png`, `1b.png`, etc.) in a folder named `figures` to keep the main directory clean.
    * `1a.png`, `1b.png`: Figure 1 (The Disease)
    * `2.png`: Figure 2 (Heatmap)
    * `3.png`: Figure 3 (The Cure)
    * `a1.png`, `a3.png`, `a4.png`, `a-bar.png`: Appendix/Diagnostic plots (The "Why")

## 🚀 How to Run

1.  Ensure you have `python` and the following libraries installed:
    ```bash
    pip install jupyter numpy pandas matplotlib scipy seaborn
    ```
2.  Launch the Jupyter Notebook:
    ```bash
    jupyter notebook newproj.ipynb
    ```
3.  Click **"Run All"** in the notebook to generate all figures and statistical outputs from scratch.

## 📄 Citation

If you use this model or refer to its findings, please cite:

> Anumula, R. A. S. S. (2025). *A Minimal Mechanistic Model of Emergent Pathological Rigidity Driven by a Metaplastic Feedback Loop*. GitHub Repository. https://github.com/revsieur/metaplastic-rigidity-model
