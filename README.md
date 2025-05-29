# End-to-End Semantic Book Recommender using LLMs 📚

This is an end-to-end project that builds an intelligent, user-friendly book recommendation system powered by large language models (LLMs) which takes in account about the user's preference for various categories and the emotional relevance they are seeking in a book.

## 📽️ Demo

Watch a quick walkthrough of the Book Recommender in action:

👉 [Demo video](https://www.dropbox.com/scl/fi/2p7pmsoug0fbt1igof8e2/Book-Recommender.mp4?rlkey=3wqhm4c19r49yzw9bb9r567sl&st=rbxsg05i&dl=0)

---

##  Project Components:

### 1.  Data Import and EDA  
**Notebook**: `data-exploration.ipynb`  
- Imported a book dataset from **Kaggle**.
- Cleaned and prepared the raw book dataset by handling missing values, removing noise and ensuring consistency. 
- Exploratory Data Analysis to make sure that there is no underlying biases in the data which could possibly influence the recommendation system in the future.
- A Good Dataset = A Good Model, layed the foundations for accurate downstream NLP tasks.

---

### 2.  Semantic Search with Vector Embeddings  
**Notebook**: `vector-search.ipynb`  
- From the preprocessed data, converted the book descriptions into high-dimensional vector embeddings using **Langchain**.(Used free embedding model: HuggingFaceEmbeddings(model_name="sentence-transformers/all-MiniLM-L6-v2").
- Built a vector database for efficient semantic search.(Chroma)
- Search can be done through Natural Language queries such as:  
  _"A book about World War."_

---

### 3.  Zero-Shot Text Classification  
**Notebook**: `text-classification.ipynb`  
- Original dataset had very messy, noisy and impractical amount of categories so cleaned and mapped a narrowed category list to capture the most relevant ones.
- Used zero-shot classification with the help of a HuggingFace pretrained model("facebook/bart-large-mnli") to categorize books as **Fiction** or **Non-Fiction**.
- Validated the accuracy of predicted categories against actual and obtained a respectable ~78% accuracy.
- All this contributed to add a useful filter for users to explore books by categories such as **Fiction**, **Non-Fiction**, **Children's fiction** and **Children's Non fiction** .

---

### 4.  Sentiment Analysis  
**Notebook**: `sentiment-analysis.ipynb`  
- Used Transformers to import a pretrained text classification model = "j-hartmann/emotion-english-distilroberta-base" which classified each book's description to 7 emotions(anger, disgust, fear, joy, sadness, surprise, neutral).
- Performed tone and emotion analysis using the model to precisely capture what the description of each book conveys.
- The tone as a whole is calculated based on how each sentence of the description has scores for each emotions and taking the max_score in account.
- This allowed users to sort and discover books based on emotional preferences.

---

### 5.  Gradio Web Interface  
**Script**: `gradio-dashboard.py`  
- Combined all the components into an interactive web application using gradio.
- Lets users:
  - Enter natural language queries(e.g. A book about two people in love.)
  - Filter results by Fiction/Nonfiction/Children's fiction/ Children's Nonfiction
  - Filter books by emotional tone
  - Get intelligent, personalized book recommendations accordingly

---


##  Installation & Setup 💻

Follow the steps below to get the app running locally:

### 1. Clone the Repository

```bash
git clone https://github.com/dishangrgbhd/End-to-End-Semantic-Book-Recommender.git
cd End-to-End-Semantic-Book-Recommender
```

### 2. Set Up a Virtual Environment 

```bash
python -m venv venv
source venv/bin/activate  # On macOS/Linux
venv\Scripts\activate    # On Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Assistant

```bash
python gradio-dashboard.py
```

---

## Contributions 🤝
💡 I’m open to feedback, issues, and contributions — feel free to fork, clone, or open a pull request! Contributions for improvements are welcomed!


