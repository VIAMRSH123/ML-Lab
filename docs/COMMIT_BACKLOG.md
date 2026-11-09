# Daily Commit Backlog

A queue of real work for this repo. A scheduled agent takes the **top unchecked item**, does it
properly, verifies it, and commits. This repo is **submitted coursework**: every change is additive.

## Rules

1. **One item per run.** Finish it or leave it uncommitted.
2. **ALLOWED:** READMEs that explain each lab (problem, how to run, what it demonstrates); a
   top-level index README; `.gitignore` entries; `requirements.txt` / environment note; dataset
   provenance and licence notes; removing clearly accidental junk.
3. **FORBIDDEN:** rewriting or "improving" any lab solution, changing an algorithm or its output,
   re-running notebooks so stored results change, reformatting submitted notebooks, renaming or
   deleting graded files. If a lab looks wrong, record it under "Observations" - do not fix it.
4. **Verify before committing.** No executable file may change. Every command a README tells a reader
   to run must be one that was actually run or is visibly correct. Describe only what the code does.
5. **No filler.** Stage named paths only (never `git add -A`). Conventional commit subject.
   Commit on `main`, push to origin.
6. Tick the item and append to the Log below.

## Audit findings (verified 2026-11-09)

- Repo has 12 lab folders (`Lab-0` .. `Lab-10`, `Lab-exam`), 15 notebooks, a MIT `LICENSE`, and a
  `README.md` containing only the title `# ML-Lab`.
- **No datasets are committed.** Notebooks read local or Colab files: `housing.csv` (Lab-0),
  `housing (1).csv` (Lab-2), `Dataset of Diabetes .csv` (Lab-1), `hiring.csv` and `1000_Companies.csv`
  (Lab-3), `/content/sample_data/insurance_data.csv` (Lab-4), `/content/drug.csv`,
  `/content/iris (1).csv`, `/content/petrol_consumption.csv` (Lab-5), `/content/diabetes.csv`,
  `/content/heart.csv`, `/content/iris (1).csv` (Lab-6), `/content/heart.csv` (Lab-10),
  `/content/mail_data.csv` (Lab-exam). Labs 7, 8, 9 use `sklearn.datasets.load_iris` (no file).
- Libraries imported across the notebooks: numpy, pandas, matplotlib, seaborn, scikit-learn, IPython.
- No `.DS_Store`, checkpoints or tracked CSVs found; no `.gitignore` exists.

## Observations (for VB to decide; do NOT change)

- `Lab-4/Logistic.ipynb`, `Lab-5/DecisionTrees.ipynb` and `Lab-6/Iris.ipynb` are **plain Python
  source saved with an `.ipynb` extension**, not valid notebook JSON, so Jupyter/Colab and GitHub's
  notebook viewer cannot open them. Left untouched because they were the submitted files.
- `Lab-5` holds two files differing only by capitalisation (`DEcisionTrees.ipynb` is a real notebook
  with outputs; `DecisionTrees.ipynb` is the plain-Python one above). Case-insensitive filesystems
  (macOS/Windows) cannot check both out.

## Queue

- [ ] **B1 - Top-level README index.** Replace the one-line README with: purpose, a table of
      Lab-0..Lab-10 + Lab-exam (notebook file, topic as read from the code, dataset used, whether it
      is committed), and how to open in Colab. Topics must be read from each notebook, not guessed.
- [ ] **B2 - `.gitignore` and `requirements.txt`.** Ignore `.ipynb_checkpoints/`, `.DS_Store`,
      `__pycache__/`, and local data dumps. Requirements list only the libraries verified above;
      check each notebook's imports again before writing it.
- [ ] **B3 - `DATASETS.md`.** Per-dataset provenance and licence notes for the files listed in the
      audit. Only state a source when it can be confirmed (e.g. sklearn's bundled iris); mark the rest
      "origin not recorded in the repo - VB to fill in". Do not fabricate sources or add data files.
- [ ] **B4 - Per-lab READMEs (Lab-0..Lab-5).** One short README per folder: problem, dataset needed
      and where to put it, how to run, what it demonstrates. Read each notebook first.
- [ ] **B5 - Per-lab READMEs (Lab-6..Lab-10, Lab-exam).** Same as B4.
- [ ] **B6 - Document the three non-notebook `.ipynb` files** in the READMEs (how to run them as
      Python scripts, e.g. `python Logistic.ipynb` after verifying it runs) without altering them.

## Log

2026-11-09 - audit - docs: add COMMIT_BACKLOG.md audit and queue
