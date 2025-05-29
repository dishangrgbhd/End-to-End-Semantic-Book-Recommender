# 📖 End-to-End Book Recommendation System using LLMs

This project is an end-to-end pipeline that builds an intelligent, user-friendly book recommendation system powered by large language models (LLMs). Starting from raw textual data, it covers everything from data preprocessing and semantic search to classification, emotion analysis, and a production-ready web interface.

---

## 🧩 Project Components

### 1. 🧼 Text Data Cleaning  
**Notebook**: `data-exploration.ipynb`  
- Cleans and prepares the raw book dataset.
- Handles missing data, removes noise, and ensures consistency.
- Lays the foundation for accurate downstream NLP tasks.

---

### 2. 🔍 Semantic Search with Vector Embeddings  
**Notebook**: `vector-search.ipynb`  
- Converts book descriptions into high-dimensional vector embeddings using LLMs.
- Builds a vector database for efficient semantic search.
- Enables natural language queries such as:  
  _"a book about a person seeking revenge"_

---

### 3. 🧠 Zero-Shot Text Classification  
**Notebook**: `text-classification.ipynb`  
- Uses zero-shot classification with LLMs to categorize books as **Fiction** or **Non-Fiction**.
- Requires no labeled training data.
- Adds a useful filter for users to explore books by type.

---

### 4. 🎭 Sentiment & Emotion Analysis  
**Notebook**: `sentiment-analysis.ipynb`  
- Performs tone and emotion analysis using LLMs.
- Extracts descriptors like *suspenseful*, *joyful*, or *sad*.
- Allows users to sort and discover books based on emotional tone.

---

### 5. 🌐 Gradio Web Interface  
**Script**: `gradio-dashboard.py`  
- Combines all the components into an interactive web application.
- Lets users:
  - Enter natural language queries
  - Filter results by fiction/non-fiction
  - Sort books by emotional tone
  - Get intelligent, personalized book recommendations

---

## 🚀 Running the Project

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/book-recommendation-llm.git
   cd book-recommendation-llm

