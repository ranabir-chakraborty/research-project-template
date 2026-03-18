# Research Project Template

This repository provides a reusable template for computational research projects using **R, Python, Google Earth Engine (GEE), Quarto, and Git**. It is designed to maintain a clean, organized, and reproducible workflow for data analysis, modeling, and manuscript preparation.

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
└── project-name.Rproj
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

---

# Environment Setup

This template supports **separate reproducible environments for Python and R**.

Environment folders are ignored by Git.

---

# Python Environment (.venv) — VS Code

### Step 1 — Open project in VS Code

Open the project folder:

```
File → Open Folder → research-project-template
```

---

### Step 2 — Open terminal

```
Terminal → New Terminal
```

---

### Step 3 — Create virtual environment

```
python -m venv .venv
```

This creates a folder:

```
.venv/
```

---

### Step 4 — Activate environment

PowerShell:

```
.venv\Scripts\activate
```

You should see:

```
(.venv)
```

before the terminal prompt.

---

### Step 5 — Install packages

Example:

```
pip install pandas geopandas matplotlib jupyter
```

---

### Step 6 — Save dependencies

```
pip freeze > python/requirements.txt
```

This records Python packages used in the project.

---

# R Environment (renv) — RStudio

### Step 1 — Open the R Project

Open:

```
project-name.Rproj
```

in **RStudio**.

---

### Step 2 — Initialize renv

Run in the R console:

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

### Step 3 — Install R packages

Example:

```r
install.packages(c("tidyverse", "sf", "terra"))
```

---

### Step 4 — Save environment

```
renv::snapshot()
```

This records package versions in `renv.lock`.

---

### Step 5 — Restore environment on another machine

```
renv::restore()
```

This installs all required packages automatically.

---

# Manuscript Workflow (Quarto)

Manuscripts are written using **Quarto (`.qmd`)**.

Example file:

```
manuscript.qmd
```

Render manuscript:

```
quarto render manuscript.qmd
```

Possible outputs:

* PDF
* Word
* HTML

Only the **source `.qmd` file is tracked in Git**.

---

# Git Workflow

Typical workflow:

1. Write scripts in `R/`, `python/`, or `gee/`
2. Process data into `data/processed/`
3. Generate figures and tables
4. Update the Quarto manuscript
5. Commit changes
6. Push to GitHub

---

# Using This Template for a New Project

1. Create a new repository from this template.
2. Clone the new repository.
3. Open the project in RStudio or VS Code.
4. Initialize `renv` and `.venv`.
5. Start analysis.

---
