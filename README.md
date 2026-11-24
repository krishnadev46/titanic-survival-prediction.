# Titanic Survival Prediction

A scikit-learn pipeline, saved as `titanic_survival_model.pkl`, that predicts whether a Titanic passenger would have survived. The included notebook loads the pipeline and runs a sample prediction.

## Files

| File | Description |
|------|-------------|
| `titanic_survival_model.pkl` | Trained scikit-learn pipeline (preprocessing + classifier) |
| `titanic_survival_model.pkl.ipynb` | Notebook with an example prediction |
| `requirements.txt` | Python dependencies |

## Setup

```bash
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

> **Important:** use the same `scikit-learn` version that was used to train the model. Pickled models can fail or behave differently across versions. If loading fails, pin the version from your training environment (e.g. `scikit-learn==1.x.x`).

## Input features

The pipeline expects a DataFrame with these columns, in this order:

| Column | Description | Example |
|--------|-------------|---------|
| `Pclass` | Ticket class (1, 2, 3) | `2` |
| `Sex` | `male` or `female` | `'male'` |
| `Age` | Age in years | `31.0` |
| `SibSp` | Number of siblings/spouses aboard | `0` |
| `Parch` | Number of parents/children aboard | `0` |
| `Fare` | Ticket fare | `10.5` |
| `Embarked` | Port: `C`, `Q`, or `S` | `'S'` |

## Usage

```python
import pickle
import pandas as pd

with open("titanic_survival_model.pkl", "rb") as f:
    pipe = pickle.load(f)

passenger = pd.DataFrame(
    [[2, 'male', 31.0, 0, 0, 10.5, 'S']],
    columns=['Pclass', 'Sex', 'Age', 'SibSp', 'Parch', 'Fare', 'Embarked']
)

print(pipe.predict(passenger))   # array([0])
```

If the model was saved with joblib, load it with `joblib.load("titanic_survival_model.pkl")` instead.

## Output

- `0` – did not survive
- `1` – survived

For probabilities (if the classifier supports it):

```python
pipe.predict_proba(passenger)
```

## Example

A 31-year-old man in 2nd class, travelling alone, fare 10.5, embarked at Southampton → predicted `0` (did not survive).

## Running the notebook

```bash
jupyter notebook
```

Open `titanic_survival_model.pkl.ipynb`. Note that the notebook uses a variable `pipe`, so run the model-loading code (see Usage) in a cell before the prediction cell.

## Notes

- Only load `.pkl` files from sources you trust, since unpickling can execute arbitrary code.
- Category values (`Sex`, `Embarked`) must match the training data spelling and case.
