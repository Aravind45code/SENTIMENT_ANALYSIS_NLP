

# 📝 Sentiment Analysis using NLP  

This project is a **Django-based Sentiment Analysis Web Application** that predicts whether a given text expresses **Positive** or **Negative** sentiment.  
It uses **Natural Language Processing (NLP)** techniques and a **Logistic Regression classifier** trained on word frequency features.

---

## ✨ Features  

- 🔤 Accepts user input text and analyzes its sentiment.  
- 📊 Uses **Logistic Regression** with pre-computed word frequencies (`freqs.pickle`, `theta.pickle`).  
- 🌐 Simple **Django web interface** to interact with the model.  
- ⚡ Deployed on **Heroku** (via `Procfile` and `runtime.txt`).  
- 🛠️ Modular code with Django apps (`polls`) for easy extension.  

---

## 📂 Project Structure  

```plaintext
SENTIMENT_ANALYSIS_NLP-main/
│── Procfile                  # For Heroku deployment
│── README.md                 # Project documentation
│── db.sqlite3                # Default Django DB (for sessions, etc.)
│── manage.py                 # Django entry point
│── nltk.txt                  # NLTK dependencies (for Heroku)
│── requirements.txt          # Python dependencies
│── runtime.txt               # Python runtime version for Heroku
│
├── mysite/                   # Django project settings
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│
├── polls/                    # Core sentiment analysis app
│   ├── Sentiment_classifier_LG.py   # Logistic Regression classifier code
│   ├── final.py                      # Helper script for training/testing
│   ├── freqs.pickle                  # Saved word frequency dictionary
│   ├── theta.pickle                  # Trained model parameters
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   ├── views.py
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository

```bash
git clone https://github.com/your-username/SENTIMENT_ANALYSIS_NLP.git
cd SENTIMENT_ANALYSIS_NLP-main
```

### 2️⃣ Create virtual environment

```bash
python -m venv venv
source venv/bin/activate   # On Mac/Linux
venv\Scripts\activate      # On Windows
```

### 3️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

### 4️⃣ Run database migrations

```bash
python manage.py migrate
```

### 5️⃣ Start the Django server

```bash
python manage.py runserver
```

Visit 👉 [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## ▶️ Usage

1. Enter text in the input form.
2. The backend (`polls/views.py`) calls **`Sentiment_classifier_LG.py`**.
3. The classifier loads `freqs.pickle` (word counts) and `theta.pickle` (model weights).
4. The text is tokenized → converted into feature vector → logistic regression predicts sentiment.
5. Result is displayed as **Positive** 👍 or **Negative** 👎.

---

## 🔑 API Endpoints

| Endpoint        | Method | Description                        |
| --------------- | ------ | ---------------------------------- |
| `/polls/`       | GET    | Home page with sentiment form      |
| `/polls/result` | POST   | Submit text → get sentiment result |

---

## 🛠️ Technologies Used

* **Backend**: Django, Python
* **ML/NLP**: Logistic Regression, NLTK
* **Frontend**: Django templates (HTML/CSS)
* **Database**: SQLite (default)
* **Deployment**: Heroku (Procfile, runtime.txt)

---

## 📊 Model Information

* Algorithm: **Logistic Regression**
* Input: Word frequency features (`freqs.pickle`)
* Parameters: Trained weights (`theta.pickle`)
* Task: **Binary Sentiment Classification** (Positive/Negative)

---

## 🚀 Deployment (Heroku)

1. Login to Heroku CLI

   ```bash
   heroku login
   ```
2. Create Heroku app

   ```bash
   heroku create your-app-name
   ```
3. Push code

   ```bash
   git push heroku main
   ```
4. Open in browser

   ```bash
   heroku open
   ```

````

