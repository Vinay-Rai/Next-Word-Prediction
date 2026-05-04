# 🔤 Next Word Prediction using LSTM

A deep learning project that predicts the **next word** in a sentence using a **Stacked LSTM model** trained on Shakespeare's *Hamlet*. The model is built with TensorFlow/Keras and deployed as an interactive web app using **Streamlit**.

---

## 🚀 Live Demo

👉 [Open App on Streamlit](https://next-word-prediction-n9t2a49v6k7n3hjco2bmgn.streamlit.app/)



---

## 📌 Features

- Trained on Shakespeare's *Hamlet* from the NLTK Gutenberg corpus
- N-gram sequence generation for training data preparation
- Stacked LSTM architecture with Dropout regularization
- Predicts the most likely next word given any input text
- Interactive web interface powered by Streamlit

---

## 🧠 How It Works

1. **Data Collection** — Shakespeare's *Hamlet* is loaded from the NLTK Gutenberg corpus and saved locally as `hamlet.txt`.
2. **Preprocessing** — The text is lowercased, tokenized, and converted into N-gram sequences. Sequences are padded to a uniform length.
3. **Model Training** — A stacked LSTM model is trained for 130 epochs on 80% of the data, with 20% held out for validation.
4. **Prediction** — Given an input phrase, the model tokenizes it, pads it, and predicts the next word using `argmax` on the softmax output.
5. **Deployment** — The trained model and tokenizer are saved and loaded by the Streamlit app for real-time inference.

---

## 🗂️ Project Structure

```
├── Experiments.ipynb        # Model training and experimentation notebook
├── app.py                   # Streamlit app entry point
├── hamlet.txt               # Raw text data (auto-downloaded via NLTK)
├── next_word_lstm.h5        # Saved trained LSTM model
├── tokenixer.pickle         # Saved Keras tokenizer
├── requirements.txt         # Python dependencies
└── README.md
```

---

## 🏗️ Model Architecture

| Layer | Details |
|-------|---------|
| Embedding | `total_words` vocab × 100 dimensions |
| LSTM (1st) | 150 units, `return_sequences=True` |
| Dropout | 0.2 rate |
| LSTM (2nd) | 100 units |
| Dense (Output) | `total_words` units, `softmax` activation |

- **Loss:** Categorical Crossentropy  
- **Optimizer:** Adam  
- **Epochs:** 130  
- **Train/Test Split:** 80% / 20%

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| TensorFlow / Keras | Model building & training |
| NLTK (Gutenberg corpus) | Dataset — Shakespeare's Hamlet |
| NumPy | Numerical operations |
| Scikit-learn | Train/test splitting |
| Pickle | Tokenizer serialization |
| Streamlit | Web app deployment |

---

## ⚙️ Installation & Local Setup

### 1. Clone the repository

```bash
git https://github.com/Vinay-Rai/Next-Word-Prediction.git
cd Next-Word-Prediction
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Streamlit app

```bash
streamlit run app.py
```

The app will open at `http://localhost:8501` in your browser.

---

## 📓 Re-training the Model

To retrain from scratch, open and run the notebook:

```bash
jupyter notebook Experiments.ipynb
```

This will:
- Download *Hamlet* via NLTK
- Preprocess and generate N-gram sequences
- Train the LSTM model for 130 epochs
- Save `next_word_lstm.h5` and `tokenixer.pickle`

---

## 💡 Example Prediction

```
Input text : "please bring me a coffee and"
Next word  : "some"   # output will vary based on training run
```

---

## 📦 Requirements

```
tensorflow
keras
nltk
numpy
scikit-learn
streamlit
```



---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
