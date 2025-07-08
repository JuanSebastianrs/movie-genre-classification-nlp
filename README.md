# NLP-Based Movie Genre Classification 🎬📚

This project uses **natural language processing** and **sentence embeddings** to classify movie plot summaries (`overview`) into genres. It was developed as part of the "Machine Learning Applications" course (MACC Master's program, Universidad del Rosario).

---

## 🎯 Objective

Use the `overview` text field to predict the movie genre via a supervised classification model. The approach includes:

- Generating sentence embeddings using `all-MiniLM-L6-v2` (from `sentence-transformers`)
- Training and evaluating a classifier using scikit-learn models
- Applying standard NLP preprocessing and dataset curation

---

## 🗃️ Dataset

We used [The Movies Dataset](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset) from Kaggle, which contains metadata for over 45,000 films. Only a subset of columns is used:

- `title`
- `overview` (plot summary)
- `genres` (filtered to 13 valid categories)

📂 See [`data/`](./data/) for column descriptions and file list. The full dataset is not included due to size and license constraints.

---

## 📈 Results

The final classifier achieved:

- **Accuracy**: ~0.60  
- **F1-score**: ~0.45  

The model performed well for major genres like Drama, Comedy, and Action.

---

## 📁 Repository Structure

```plaintext
notebook/           # Jupyter notebook for training and testing
report/             # Formal report in PDF (in Spanish)
data/               # CSV files (optional, see README.md inside)
requirements.txt    # List of Python dependencies
