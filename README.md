# 🎭 Emotion Classification with Attention

## 📌 Project Overview

An AI-powered **Emotion Classification System** that identifies emotions in text using Deep Learning and Transformer-based models.

The project implements and compares four different neural network architectures to classify text into six emotion categories.

A Streamlit web application provides an interactive interface for real-time emotion prediction.

## 🎯 Project Objectives

- Build a multi-model text emotion classification system.
- Apply Natural Language Processing (NLP) techniques.
- Implement Deep Learning models using TensorFlow/Keras.
- Fine-tune a pretrained Transformer model using Hugging Face.
- Compare model performance using standard evaluation metrics.
- Visualize attention weights to interpret important words.
- Deploy the best-performing model through Streamlit.

## 📊 Dataset

**Dataset:** [GoEmotions – Google Research](https://huggingface.co/datasets/google-research-datasets/go_emotions)

The original dataset contains 27 emotion categories plus Neutral.

For this project, the original categories were mapped into six target emotions:

| Emotion  | Original Categories                                                              |
| -------- | -------------------------------------------------------------------------------- |
| Joy      | Joy, Amusement, Excitement, Love, Optimism, Pride, Relief, Gratitude, Admiration |
| Sadness  | Sadness, Grief, Disappointment, Remorse                                          |
| Anger    | Anger, Annoyance, Disapproval                                                    |
| Fear     | Fear, Nervousness                                                                |
| Surprise | Surprise                                                                         |
| Disgust  | Disgust                                                                          |

Samples with no mapped target emotion or multiple mapped target emotions were excluded to create a single-label classification dataset.

### Final Dataset Distribution

- Training: 22,386 samples
- Validation: 2,766 samples
- Testing: 2,781 samples
- Total: 27,933 samples

## 🧠 Models Implemented

Four models were developed and evaluated:

1. **LSTM (Long Short-Term Memory)**

   - Uses GloVe 100-dimensional word embeddings.
   - Captures sequential dependencies in text.

2. **GRU (Gated Recurrent Unit)**

   - Uses pretrained GloVe embeddings.
   - Provides an efficient recurrent architecture.

3. **BiLSTM + Attention**

   - Processes text in both forward and backward directions.
   - Uses an Attention mechanism to assign weights to important tokens.
   - Includes attention visualization for model interpretability.

4. **DistilBERT**

   - Based on `distilbert-base-uncased`.
   - Fine-tuned for six-class emotion classification.
   - Implemented using Hugging Face Transformers and PyTorch.

## 📈 Model Performance Comparison

All models were evaluated on the same held-out test dataset.

| Model              |   Accuracy |   Macro F1 |
| ------------------ | ---------: | ---------: |
| **DistilBERT**     | **85.76%** | **73.48%** |
| GRU                |     77.78% |     64.85% |
| BiLSTM + Attention |     76.88% |     64.52% |
| LSTM               |     77.06% |     64.23% |

### Best Performing Model

**DistilBERT achieved the best overall performance**, with:

- Test Accuracy: 85.76%
- Test Macro F1: 73.48%

DistilBERT outperformed the recurrent models on both evaluation metrics.

## 🔍 Model Interpretability

The BiLSTM + Attention model includes an Attention mechanism that assigns weights to input tokens.

Attention weights are visualized through heatmaps to highlight words receiving higher attention scores.

This provides an additional interpretability view of the model's behavior.

## 🖥️ Streamlit Web Application

The project includes an interactive Streamlit application that supports:

- Text input for emotion analysis.
- Selection between the four trained models.
- Real-time emotion prediction.
- Confidence score visualization.
- Emotion probability charts.
- Model performance comparison.

### Application Screenshot

Add your Streamlit application screenshot here:

## 🛠️ Technologies & Tools

- Python
- TensorFlow / Keras
- PyTorch
- Hugging Face Transformers
- Scikit-learn
- GloVe Word Embeddings
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Streamlit
- Kaggle

## 📁 Project Structure

```text
Emotion-Classification-with-Attention/
│
├── app.py
├── requirements.txt
├── README.md
├── .gitignore
├── model_comparison.csv
│
└── images/
    └── app_screenshot.png
```

**Note:** Trained model weights and large model artifacts are not included in this GitHub repository because of file size limitations.

## ⚙️ Installation & Usage

### 1. Clone the Repository

```bash
https://github.com/tarek-sabry/Emotion-Classification-with-Attention
```

### 2. Navigate to the Project Directory

```bash
cd Emotion-Classification-with-Attention
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Download Model Files

Download the trained model files and supporting artifacts from the Kaggle notebook linked below.

Place them in the project directory using the paths expected by `app.py`.

### 5. Run the Streamlit Application

```bash
streamlit run app.py
```

## 📓 Kaggle Notebook

The complete project implementation, including dataset preparation, preprocessing, model training, evaluation, attention visualization, and saved model artifacts, is available on Kaggle:

[Emotion Classification with Attention – Kaggle Notebook](https://www.kaggle.com/code/tareksabry/emotion-classification-with-attention)

## 📌 Key Findings

- DistilBERT achieved the highest Accuracy and Macro F1.
- GRU achieved the best performance among the three recurrent models.
- BiLSTM + Attention provided an attention-based interpretability component.
- Class imbalance affected performance across the six emotion categories.
- Macro F1 was used alongside Accuracy to provide a more balanced evaluation.

## 👨‍💻 Author

**Tarek Sabry**

Data Science & AI | Machine Learning | Deep Learning | NLP

---

⭐ If you find this project interesting, feel free to explore the repository and Kaggle notebook.
