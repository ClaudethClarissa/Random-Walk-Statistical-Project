# Two-Dimensional Random Walks | Statistical Analysis

**Python · Statistical Analysis · Stochastic Processes · Data Visualization**

## Overview

This project examines two-dimensional random walks by comparing particle trajectories under symmetric and directionally biased movement probabilities. The analysis uses stored trajectories for **100 particles per scenario**, with **10,000 recorded positions per particle**, and investigates how changes in step probabilities affect the distribution of particle positions.

The motivation is relevant to stochastic transport and biophysics, where directional bias may arise in the presence of an external gradient.

[**Explore the statistical analysis notebook**](Caminante%20semi-aleatorio.ipynb) · [**View the project poster**](Poster_Congreso.pdf)

## Research Questions

- How do endpoint positions vary across independent random-walk trajectories?
- What differences emerge between symmetric motion and directional bias?
- How do the position distributions compare at an early observation and at the end of the trajectories?
- How well do observed coordinate distributions agree with a Gaussian approximation?

## Simulation Conditions

The repository contains particle-coordinate files for four experimental conditions. The labels indicate the nominal probability of taking a positive-direction step in each coordinate.

| Condition | Positive X step | Positive Y step | Trajectories |
|---|---:|---:|---:|
| Symmetric | 50% | 50% | 100 |
| Biased in X and Y | 55% | 55% | 100 |
| Biased in X only | 60% | 50% | 100 |
| Stronger bias in X and Y | 60% | 60% | 100 |

Each trajectory file records positions in columns **X** and **Y**. The notebook compares positions at approximately step 100 and at the final recorded position, alongside selected full trajectories.

## Methodology

1. Load the trajectory files for each probability condition using pandas.
2. Extract particle positions at selected observation indices.
3. Calculate descriptive statistics for the X and Y coordinates.
4. Compare coordinate distributions using boxplots and histograms.
5. Apply Shapiro–Wilk tests and fit Gaussian distributions to coordinate samples.
6. Plot selected trajectories to illustrate symmetric and biased motion.
7. Explore samples of generated random numbers stored separately in the repository.

The analysis is exploratory. A Shapiro–Wilk result alone does not establish that a distribution is exactly Gaussian, and the independence assumptions and coordinate-wise interpretation matter.

## Analysis Notebook

[**Caminante semi-aleatorio.ipynb**](Caminante%20semi-aleatorio.ipynb)

This is the main analysis, including code, descriptive summaries, statistical tests and **34 saved plot outputs**. The existing notebook contains Spanish commentary; an English-language review and compatibility audit are planned without replacing the statistical analysis.

## Reports

- [**Statistics report**](Estad%C3%ADstica.pdf)
- [**Conference poster**](Poster_Congreso.pdf)

These documents provide additional context alongside the notebook.

## Repository Structure

```text
Random-Walk-Statistical-Project/
├── Caminante semi-aleatorio.ipynb    # Main statistical analysis
├── Estadística.pdf                  # Statistical report
├── Poster_Congreso.pdf               # Conference poster
├── Números Aleatorios/               # Stored random-number samples
├── Partículas con 50% y 50%/         # 100 trajectories
├── Partículas con 55% y 55%/         # 100 trajectories
├── Partículas con 60% y 50%/         # 100 trajectories
├── Partículas con 60% y 60%/         # 100 trajectories
└── README.md
```

## How to Explore the Project

Install Python with `numpy`, `pandas`, `scipy`, `matplotlib` and Jupyter:

```bash
python -m pip install numpy pandas scipy matplotlib notebook
jupyter notebook "Caminante semi-aleatorio.ipynb"
```

Run the notebook from the **repository root**, keeping the existing trajectory folders alongside it. The data files are already stored in the repository.

## Limitations

- The analysis uses a finite ensemble of 100 trajectories per scenario; results fluctuate across samples.
- The data-loading code and notebook outputs have not yet been re-executed in a clean environment with current dependency versions.
- The notebook accesses specific observation indices, so interpretations should distinguish zero-based indices from step numbers.
- Gaussian-fit and Shapiro–Wilk results describe individual coordinate samples; they do not by themselves establish a two-dimensional joint distribution.
- The stored trajectory dataset is large. Its full inclusion supports inspection but makes cloning the repository heavier.

---

**Portfolio:** [Data Science & Analytics Portfolio](https://github.com/ClaudethClarissa/data-science-portfolio)
