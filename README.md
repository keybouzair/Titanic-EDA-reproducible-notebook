# Titanic EDA — Who Survived, and Why?

A short, reproducible exploratory data analysis (EDA) of the classic Titanic
passenger dataset. This is a portfolio piece — the goal isn't to beat a
benchmark, it's to show clean, well-reasoned data-cleaning and a findings
section that actually answers a question with evidence.

**No modeling here.** This is EDA-only: load → clean (with rationale) →
visualize → summarize.

## What's in this repo

```
.
├── README.md
├── requirements.txt
├── data/
│   └── titanic.csv          # raw dataset, loaded via relative path
└── titanic_eda.ipynb         # the notebook — start here
```

## How to run it

```bash
git clone <this-repo-url>
cd titanic-eda
python3 -m venv venv && source venv/bin/activate   # optional but recommended
pip install -r requirements.txt
jupyter notebook titanic_eda.ipynb
```

Then `Kernel → Restart & Run All`. It runs top-to-bottom with no manual steps
and no absolute paths — the CSV is read from `data/titanic.csv` relative to
the repo root.

## What the notebook covers

1. **Load** — one cell, one dataframe, no hidden state.
2. **First look** — dtypes and a missingness table, so cleaning decisions are
   driven by what's actually in the data rather than assumption.
3. **Cleaning** — each step (Age imputed by class median, Cabin converted to
   a presence flag, Embarked mode-filled, family-size engineered, etc.) is
   commented with *why*, not just *what*.
4. **EDA** — five focused charts answering: does sex, class, age, or
   traveling alone best explain survival, and how do they interact?
5. **Findings** — a 150-word summary of the "who survived and why" story.
6. **Next steps** — what I'd do with more time (significance testing, title
   extraction from names, a sanity-check logistic regression, cabin-deck
   analysis).

## Dataset

Standard Titanic passenger manifest (891 rows, one row per passenger):
`PassengerId`, `Survived`, `Pclass`, `Name`, `Sex`, `Age`, `SibSp`, `Parch`,
`Ticket`, `Fare`, `Cabin`, `Embarked`.

## Tech

Python, pandas, NumPy, matplotlib, seaborn, Jupyter.
