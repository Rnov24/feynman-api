<div align="center">

# Feynman API: Master Any Concept Through Active Learning 🎓

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000)
![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.103.0-009688.svg)
![Instructor](https://img.shields.io/badge/Instructor-1.0.0-orange.svg)
![Gemini 2.0](https://img.shields.io/badge/Gemini-2.0-red.svg)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

</div>

<p align="center">
  <img src="assets/logo.png" alt="Feynman API Banner" width="250"/>
</p>

---

Feynman API is an AI-powered learning assistant designed to help users deeply understand complex topics by breaking them down and explaining them in their own words. Inspired by the Feynman Technique, this API challenges users with thought-provoking hints rather than direct corrections, fostering critical thinking and reinforcing comprehension through an iterative learning process.

---

## ✨ Key Features

- **🔍 General-to-Atomic** – Converts a broad topic into several specific atomic topics.
- **🧠 Understanding Analysis** – Determines the user's comprehension level based on their initial explanation.
- **🤔 Clue-Based Feedback** – Provides skeptical questions to help users identify gaps in their explanations.
- **🔄 Iterative Learning Until Goals Are Met** – The process repeats until the explanation meets the required standard.
- **🚀 Stateless & Fast** – No session tracking, making it easy to integrate with various applications.
- **🛑 Adjustable Rate Limiting** – Configurable rate limit per user/IP to maintain stability and flexibility.

---

## 🔧 Tech Stack

Feynman API is built using modern and efficient technologies that work seamlessly together:

- **FastAPI** – High-performance web framework for building APIs.
- **Instructor** – Structured API responses with ease.
- **Gemini 2.0** – AI model for goal generation and feedback.
- **Uvicorn** – Lightning-fast ASGI server for running FastAPI applications.
- **Redis (optional)** – Can be used for rate limiting and caching.
- **Docker (optional)** – Containerized deployment for scalability.

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/username/feynman-api.git
cd feynman-api
```

### 2️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Run the Server
```bash
uvicorn main:app --reload
```

### 4️⃣ Access API Documentation
Open [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs) in your browser to explore and test the API.

---

## 📌 How It Works

1. User submits a **general topic** → API returns multiple **atomic topic** choices.
2. User selects an **atomic topic** and provides an **initial explanation**.
3. The model determines a **goal** based on the user's initial understanding and immediately provides **clue-based feedback**.
4. User iteratively submits **explanations**, refining their understanding based on the feedback.
5. The process continues until the **explanation meets the goal**.

---

## 📡 API Endpoints

### 1️⃣ Generate Atomic Topics
- **Endpoint:** `POST /generate_atomic`
- **Request:**
  ```json
  {
    "general_topic": "Quantum Physics"
  }
  ```
- **Response:**
  ```json
  {
    "atomic_topics": [
      "Heisenberg Uncertainty Principle",
      "Schrödinger's Equation",
      "Wave-Particle Duality"
    ]
  }
  ```

### 2️⃣ Start Learning Session
- **Endpoint:** `POST /start_session`
- **Request:**
  ```json
  {
    "atomic_topic": "Heisenberg Uncertainty Principle",
    "initial_explanation": "When we measure position and momentum..."
  }
  ```
- **Response:**
  ```json
  {
    "message": "Session started",
    "goal": "Explain the relationship between measurement and uncertainty in quantum mechanics.",
    "feedback": "How does measurement influence the uncertainty of a system?"
  }
  ```

### 3️⃣ Submit Explanation
- **Endpoint:** `POST /submit_explanation`
- **Request:**
  ```json
  {
    "explanation": "The Heisenberg Uncertainty Principle states that...",
    "goal": "Explain the relationship between measurement and uncertainty in quantum mechanics."
  }
  ```
- **Response:**
  ```json
  {
    "feedback": "Are you sure uncertainty only applies to small particles?",
    "is_goal_met": false
  }
  ```

### 4️⃣ Check Goal Completion
- **Endpoint:** `GET /check_goal`
- **Response:**
  ```json
  {
    "is_goal_met": true,
    "message": "Congratulations! You have successfully explained this concept."
  }
  ```

---

## 🎯 Why Use Feynman API?
✅ **Active Learning** – Develop deeper understanding by teaching the concept in your own words.
✅ **Guided Feedback** – Receive hints that prompt you to refine your explanations instead of direct corrections.
✅ **Adaptive to Your Level** – The model adjusts goals based on your initial understanding.
✅ **Easy to Integrate** – A simple, stateless JSON-based API that fits into any learning platform.

---

## 📜 License
This project is released under the **MIT License**. Free to use and modify!

🚀 **Feynman API – Because the best way to learn is to teach!**.

