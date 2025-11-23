# 📄 Intelligent Resume Screening System

A Flask-based AI tool for matching and ranking resumes against a given job description using NLP and cosine similarity.

This project extracts text from uploaded resumes (PDF, DOCX, TXT), converts them into TF-IDF vectors, and compares them with a job description to identify the **top matching resumes** automatically.

---

## 🚀 Features

### ✔ Resume Text Extraction

Supports:

* PDF (.pdf)
* Word Document (.docx)
* Text File (.txt)

### ✔ NLP-Based Matching

Uses:

* **TF-IDF Vectorization**
* **Cosine Similarity**

### ✔ Ranks Resume Automatically

Outputs the **Top 5 matching resumes** based on similarity score.

### ✔ Flask Web Interface

Simple UI for:

* Uploading multiple resumes
* Entering job description
* Viewing top matches

---

## 🧠 How It Works

1. User enters a **job description**.
2. User uploads **multiple resume files**.
3. System extracts text from each file.
4. The system converts:

   * Job description
   * Resume text
     into TF-IDF vectors.
5. Computes **cosine similarity** between job description and each resume.
6. Displays:

   * Top 5 matching resumes
   * Similarity scores

---

## 📂 Project Folder Structure

```
resume-screening/
│
├── app.py                     # Main Flask application
├── templates/
│   └── matchresume.html       # Frontend HTML file
├── uploads/                   # Uploaded resumes stored here
├── README.md                  # Project documentation
```

---

## 🛠️ Tech Stack

| Component         | Technology Used   |
| ----------------- | ----------------- |
| Backend Framework | Flask             |
| NLP               | TF-IDF Vectorizer |
| ML Similarity     | Cosine Similarity |
| PDF Extraction    | PyPDF2            |
| DOCX Extraction   | docx2txt          |
| File Uploading    | Flask + HTML      |

---

## 📥 Installation & Setup

### 1️⃣ Clone or Download the Project

```bash
git clone <your-repo-url>
cd resume-screening
```

### 2️⃣ Install Dependencies

```bash
pip install Flask docx2txt PyPDF2 scikit-learn
```

### 3️⃣ Create Uploads Folder (if missing)

```bash
mkdir uploads
```

### 4️⃣ Run the Application

```bash
python app.py
```

### 5️⃣ Open in Browser

Go to:

```
http://127.0.0.1:5000/
```

---

## 🧪 Example Output

After uploading resumes & adding a job description, the system displays:

```
Top matching resumes:
1) resume1.pdf — 0.89
2) resume2.docx — 0.82
3) resume3.pdf — 0.77
...
```

---

## 🧩 Core Code (Explanation)

### 📌 Text Extraction

* PDF → PyPDF2
* DOCX → docx2txt
* TXT → open file

### 📌 Vectorization

```python
vectorizer = TfidfVectorizer().fit_transform([job_description] + resumes)
```

### 📌 Matching

```python
similarities = cosine_similarity([job_vector], resume_vectors)[0]
```

### 📌 Top Resume Selection

```python
top_indices = similarities.argsort()[-5:][::-1]
```

---

## 🎯 Future Enhancements (Optional)

* Add **spaCy** for named entity extraction
* Use **HuggingFace Transformers** (BERT, SBERT embeddings)
* Implement **PDF layout parsing**
* Add **job role prediction**
* Build a dashboard for HR teams

---

## 👨‍💻 Author

Developed by **Amaan**
Flask • NLP • Machine Learning • Resume Matching System

---

## ⭐ If you find this helpful

Consider giving the repo a **star ⭐**!
