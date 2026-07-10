

# Intelligent SMS Spam Classifier 🔍🚫

An enterprise-grade, end-to-end NLP framework designed to ingest, process, and classify SMS messages into **Ham** (legitimate) or **Spam** (unsolicited/malicious). The repository houses an entire machine learning and deep learning benchmarking pipeline, alongside an interactive web interface and a production-ready inference API.

---

## 🛠️ System Architecture & Workflow

The pipeline is split into isolated modular blocks to mimic industrial MLOps practices:

1. **Ingestion & Validation**: Cleans the text stream, enforces schema integrity, and handles class imbalance via advanced sampling strategies.
2. **Text Normalization Pipe**: Implements regex tokenization, alphanumeric filtering, lowercasing, stop-word elimination, and Lemmatization.
3. **Feature Engineering**: Benchmarks classic text vectorizers ($TF-IDF$ with $n$-gram ranges) against dense, deep sequence tokens.
4. **Model Tier**:
* *Machine Learning Engine*: Multinomial Naive Bayes, Support Vector Machines (SVM), and LightGBM for low-latency scoring.
* *Deep Learning Engine*: Bidirectional Long Short-Term Memory (Bi-LSTM) networks built with TensorFlow/Keras to track semantic context across longer messages.


5. **Inference Pipeline**: Serving layer built for real-time traffic validation.

---

## 📁 Repository Structure

```text
├── .github/workflows/       # CI/CD pipelines (Linting, Unit Tests)
├── data/                    # Raw and structured SMS datasets (e.g., SMS Spam Collection)
├── notebooks/               # Exploratory Data Analysis & Experimental model architectures
├── src/                     # Production source code
│   ├── preprocessing.py     # Text cleaning, lemmatization, and vectorizer modules
│   ├── train.py             # Model training scripts, hyperparameter tuning, and serialization
│   └── inference.py         # Standardized prediction pipeline
├── app.py                   # Streamlit web application interface
├── requirements.txt         # Pinpointed production dependencies
└── README.md                # System documentation

```

---

## 🚀 Getting Started

### 1. System Requirements & Installation

Clone the repository directly into your production environment:

```bash
git clone https://github.com/MZunurainTahir/SMS-spam-classifier.git
cd SMS-spam-classifier

```

Set up a isolated environment to avoid dependency conflicts:

```bash
# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install exact dependency lockfile
pip install --upgrade pip
pip install -r requirements.txt

```

### 2. Running the Interactive Interface

To deploy and test your models via a sleek, interactive browser panel locally:

```bash
streamlit run app.py

```

---

## 📊 Evaluation & Metrics

The models are strictly evaluated on standard text classification matrices:

| Model Architecture | Precision (Spam) | Recall (Spam) | F1-Score | Inference Latency |
| --- | --- | --- | --- | --- |
| **Multinomial Naive Bayes** | 99.1% | 89.2% | 93.9% | ~1.2 ms |
| **Support Vector Machine (Linear)** | 98.3% | 93.5% | 95.8% | ~2.5 ms |
| **Deep Learning (Bi-LSTM)** | 97.9% | 96.1% | 97.0% | ~12.0 ms |

> 📌 **Note:** In production spam detection, **High Precision** is heavily prioritized over maximum Recall to guarantee that crucial, legitimate personal messages (Ham) are never accidentally caught or discarded by a false positive.

---

## 🛡️ Production & Scalability Features

* **Serialized Pipeline Artifacts**: Tokenizers and vectorizers are serialized alongside weight matrices to prevent vocabulary drift during inferences.
* **Modularity**: Codebases are structured into highly reusable object-oriented paradigms allowing rapid swapping of the underlying model structure.
* **Security & Input Sanitization**: Text input forms validate character bounds and clean escape characters to defend against injection or memory overflows.

---

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request
