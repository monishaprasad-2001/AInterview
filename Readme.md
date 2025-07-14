# 🧠 AInterview – AI-Powered Interview Evaluator

AInterview is a real-time AI-powered interview evaluation platform built using Spring Boot, Docker, and FastAPI microservices. It provides semantic scoring, sentiment detection, and transcribed feedback to help recruiters evaluate candidates fairly and efficiently via a clean HTML interface.

---

## 🚩 Problem Statement

Traditional interviews are resource-intensive, subjective, and inconsistent. Recruiters often face challenges in evaluating large volumes of candidate responses with fairness and accuracy.

**AInterview** addresses this gap by offering a scalable, AI-driven evaluation system that:
- Scores candidate answers based on semantic similarity to ideal responses.
- Provides insights into sentiment and emotions.
- Delivers structured, automated feedback in real time.

---

## 💡 Why This Project?

- Recruiters need **faster**, **unbiased**, and **consistent** evaluation tools.
- Candidates deserve **objective feedback** and practice opportunities.
- Organizations benefit from **reduced hiring cycles** and **higher-quality filtering**.

---

## 🚀 Key Features

- ✅ Upload or record candidate interview responses (audio or text)
- ✅ Real-time transcription using OpenAI Whisper
- ✅ Semantic similarity scoring using SBERT
- ✅ Sentiment and emotion detection
- ✅ Structured feedback display in HTML frontend
- ✅ Fully containerized deployment with Docker
- ✅ PDF download of results (optional)
- ✅ Modular backend with Spring Boot and FastAPI

---

## 🛠️ Tech Stack

| Layer        | Technology                          |
|-------------|--------------------------------------|
| Backend      | Spring Boot (Java 17)               |
| ML Service   | FastAPI (Python)                    |
| Transcription| OpenAI Whisper API                  |
| NLP Models   | Sentence-BERT, Sentiment Classifier |
| Frontend     | HTML, CSS, JavaScript               |
| DevOps       | Docker, Docker Compose              |
| Optional DB  | PostgreSQL (for future enhancements)|

---

## 🧱 Folder Structure

```
ai-interview-evaluator/
├── backend/                  # Spring Boot app (API & logic)
│   └── src/main/resources/static/evaluation.html
├── ml-service/              # FastAPI microservice (semantic score, sentiment, etc.)
├── audio/                   # (Optional) Stores audio responses
├── docker-compose.yml       # Multi-container orchestration
└── README.md
```

---

## ⚙️ How to Run

### Prerequisites

- Java 17+
- Python 3.10+
- Docker & Docker Compose
- npm (if expanding frontend)

### 🔁 Option 1: Dockerized Setup (Recommended)

```bash
git clone https://github.com/yourusername/ai-interview-evaluator.git
cd ai-interview-evaluator
docker-compose up --build
```

🔗 Access the app at:  
`http://localhost:8080/evaluation.html`

### ⚙️ Option 2: Manual Run (Dev Mode)

1. **Start ML Microservice**
   ```bash
   cd ml-service
   uvicorn main:app --host 0.0.0.0 --port 8001
   ```

2. **Run Spring Boot App**
   ```bash
   cd backend
   ./mvnw spring-boot:run
   ```

3. **Open in Browser**
   ```
   http://localhost:8080/evaluation.html
   ```

---

## 🧪 Sample Evaluation Flow

1. Candidate provides an answer (text/audio).
2. Whisper API transcribes the audio (if provided).
3. Backend forwards question and answer to ML service.
4. ML service returns:
   - Semantic score (SBERT)
   - Sentiment label (positive, negative, neutral)
   - Emotion label (happy, calm, anxious, etc.)
   - Feedback summary
5. Results displayed in browser with **PDF download** option.

---

## 🔍 Sample API Call

### POST `/api/evaluate`

**Request:**
```json
{
  "question": "Describe a challenging project you worked on.",
  "candidateAnswer": "I led a cross-functional team to build a data pipeline..."
}
```

**Response:**
```json
{
  "semanticScore": 0.87,
  "sentiment": "positive",
  "emotion": "focused",
  "feedback": "Strong technical depth and good leadership demonstration."
}
```

---

## 📈 Future Enhancements

- 🎤 Live voice interview module
- 🧠 GPT-based feedback generator
- 📄 Resume & JD integration for smarter prompts
- 🖨️ PDF reports auto-email to HR
- 📊 Admin dashboard for bulk scoring

---

## 📎 PDF Download

After evaluation, users can **download a PDF report** with:
- Semantic score
- Sentiment/emotion labels
- Full Q&A transcript
- Feedback summary

(Feature already integrated in evaluation page)

---
