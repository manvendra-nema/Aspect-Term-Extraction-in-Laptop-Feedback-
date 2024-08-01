# 🎯 Task 2: Aspect Term Extraction from Laptop Review Texts 💻



### 📝 Example
- **Text:** One night I turned the freaking thing off after using it, the next day I turn it on, no GUI, screen all dark, power light steady, hard drive light steady and not flashing as it usually does.
- **Aspect Terms:** GUI, screen, power light, hard drive light

## 📂 Dataset
- **Source:** [Laptop Review Dataset](https://laptop-review-dataset-link)
- **Files:** Three JSON files (train, validation, and test data), each containing a list of dictionaries. The `raw_words` key contains the review text, and the `aspects` key contains all the aspect terms and their span indices.

## 📊 Evaluation Metrics
- Macro-F1
- Accuracy

---

## 🛠️ Part 1: Data Preparation 

### B) Dataset Preparation 
1. Implement BIO (Beginning-Intermediate-Outside) chunking for the dataset. Tokenize based on space and assign BIO labels (B, I, O).
2. Save the processed data in the following format:
    ```json
    {
      "1": {
        "text": "This laptop meets every expectation and Windows 7 is great!",
        "labels": ["O", "O", "O", "O", "O", "O", "B", "I", "O", "O", "O"]
      },
      // More reviews
    }
    ```
3. Save processed data in JSON files for train, validation, and test splits.

---

## 🧠 Part 2: Baseline Models Implementation 

### Models
1. **Model 1:** Vanilla RNN 🧩
2. **Model 2:** LSTM 🔄
3. **Model 3:** GRU 🔗

### Pre-trained Word Embeddings
- word2vec 🌐
- GloVe 🧤
- fasttext ⚡

### Tasks
1. Train 9 models (3 models x 3 embeddings).
2. Generate the following plots for each model:
    - 📉 Training and Validation Loss vs. Epochs
    - 📈 Training and Validation Macro-F1 Score vs. Epochs
3. Load trained models, extract aspect terms from the test data, and report overall accuracy and macro-F1 scores.

---

## 💡 Part 3: BiLSTM-CRF Model Implementation 

### Model 4: BiLSTM-CRF 📊
- Implement the BiLSTM-CRF model as described in the reference paper.
- Use three different pre-trained word embeddings (word2vec, GloVe, fasttext) and train a total of three models.

### Tasks
1. Train and save the models.
2. Generate the following plots for each model:
    - 📉 Training and Validation Loss vs. Epochs
    - 📈 Training and Validation Macro-F1 Score vs. Epochs
3. Load trained models, extract aspect terms from the test data, and report overall accuracy and macro-F1 scores.
4. Calculate label-wise F1 scores for the best-performing model and plot a bar graph or pie chart.

---
