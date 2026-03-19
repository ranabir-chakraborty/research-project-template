# Research Project Template

This repository provides a reusable template for computational research projects using **R, Python, Google Earth Engine (GEE), Quarto, and Git**.

It is designed to maintain a **clean, organized, and reproducible workflow** for data analysis, modeling, and manuscript preparation.

---

# Project Structure

```
research-project-template/
├── data/
│   ├── raw/           # Original data (not tracked by Git)
│   └── processed/     # Cleaned and processed datasets
├── docs/              # Documentation and notes
├── figures/           # Generated figures
├── gee/               # Google Earth Engine scripts
├── python/            # Python scripts
├── R/                 # R scripts
├── tables/            # Output tables
├── manuscript.qmd     # Quarto manuscript
├── README.md
└── project.Rproj
```

---

# Purpose

This template helps to:

* organize research projects consistently
* separate raw data, scripts, and outputs
* support **R and Python workflows**
* support **Google Earth Engine scripts**
* generate manuscripts using **Quarto**
* maintain **version control using Git and GitHub**
* ensure **reproducible computational research**

---

# Environment Setup

This template uses **project-specific environments** for both Python and R.

These environments are **ignored by Git**.

---

# Python Environment (.venv)

### Step 1 — Open project in VS Code

```
File → Open Folder → research-project-template
```

---

### Step 2 — Create virtual environment

```
python -m venv .venv
```

---

### Step 3 — Activate environment

PowerShell:

```
.venv\Scripts\activate
```

Terminal prompt should show:

```
(.venv)
```

---

### PowerShell activation error (if occurs)

If you see:

```
running scripts is disabled on this system
```

Run once:

```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

Then activate again:

```
.venv\Scripts\Activate.ps1
```

---

### Install packages

Example:

```
pip install pandas geopandas matplotlib jupyter
```

---

### Save dependencies

```
pip freeze > python/requirements.txt
```

---

### Restore Python environment later

```
python -m venv .venv
.venv\Scripts\activate
pip install -r python/requirements.txt
```

---

# R Environment (renv)

### Step 1 — Open project in RStudio

Open:

```
project.Rproj
```

---

### Step 2 — Initialize environment

```r
install.packages("renv")
renv::init()
```

This creates:

```
renv/
renv.lock
```

---

### Install packages

```r
install.packages(c("tidyverse", "sf", "terra"))
```

---

### Save R environment

```r
renv::snapshot()
```

---

### Restore R environment later

```r
renv::restore()
```

---

# Manuscript Workflow (Quarto)

Manuscripts are written using **Quarto (.qmd)**.

Example:

```
manuscript.qmd
```

Render manuscript:

```
quarto render manuscript.qmd
```

Possible outputs:

* HTML
* PDF
* Word

Only the **source `.qmd` file is tracked in Git**.

---

# Git Workflow

Typical workflow:

```
git status
git add .
git commit -m "Describe your change"
git pull origin main --rebase
git push
```

---

# Data Management

```
data/raw/        → original datasets (not tracked)
data/processed/  → cleaned datasets
```

Large datasets should **not be pushed to GitHub**.

---

# Using This Template

1. Open the template repository
2. Click **Use this template**
3. Create a new repository
4. Clone the repository locally

Example:

```
git clone https://github.com/USERNAME/new-project.git
```

Then initialize environments and start analysis.

---

# Reproducibility

This template ensures reproducibility through:

```
Python → requirements.txt
R → renv.lock
Git → version control
Quarto → reproducible reports
```

---

# License

# License

This project is licensed under the MIT License. See the LICENSE file for details.