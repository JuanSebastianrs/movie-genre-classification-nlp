# Movie Genre Classification with Sentence Embeddings

**Predict a movie's genre from its plot summary using sentence embeddings and supervised classifiers.**

Academic project from the Machine Learning Applications course in the MACC master's program, Universidad del Rosario.

[Experiment notebook](notebook/proyecto.ipynb) · [Project report](report/Proyecto.pdf) · [Data files](data/)

## Method

1. Filter movie metadata to non-empty plot summaries and movies with exactly one genre.
2. Retain the **12 categories defined in the notebook**.
3. Keep summaries that fit a single token chunk.
4. Encode text with `sentence-transformers/all-MiniLM-L6-v2`.
5. Compare Logistic Regression, Linear SVC, Random Forest and MLP classifiers.
6. Tune on the training partition using stratified cross-validation and evaluate on the held-out test set.

The notebook uses an 80/20 stratified train/test split with a fixed random seed and selects models using macro F1.

## Reported results

The original project summary reports approximately **0.60 accuracy** and **0.45 F1**. Use the [notebook](notebook/proyecto.ipynb) and [report](report/Proyecto.pdf) for the detailed experiment context.

This is a single-label classification experiment after filtering multi-genre movies, rather than a general multi-label movie tagger.

## Explore the project

```bash
git clone https://github.com/JuanSebastianrs/movie-genre-classification-nlp.git
cd movie-genre-classification-nlp
jupyter lab
```

Open `notebook/proyecto.ipynb` and use the repository root as the notebook working directory, so that paths to `data/` resolve correctly. The notebook currently uses a Windows-style CSV path.

The [requirements file](requirements.txt) is currently empty. Reproduction needs an environment compatible with the notebook imports, including pandas, NumPy, PyTorch, scikit-learn, sentence-transformers, XGBoost and its legacy LangChain text-splitter import. A locked, validated environment specification is still needed for reproducible execution.

## Data

Source: [The Movies Dataset](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset).

The repository contains CSV files under [data/](data/), including movie metadata and supporting tables. Consult the upstream dataset's terms before reusing or redistributing them.

## Layout

```text
notebook/proyecto.ipynb  # Data curation, embeddings, model selection and evaluation
report/Proyecto.pdf     # Academic report in Spanish
data/                   # Published CSV files
requirements.txt        # Environment specification still to be completed
```

## Resumen en español

Clasificación de géneros cinematográficos a partir de sinopsis mediante embeddings y modelos supervisados. El experimento filtra películas a una sola etiqueta y compara clasificadores con validación cruzada estratificada.
