# 📧 Email Assistant — AI-Powered Email Reply Generator

An AI-powered email reply generator built with **Spring Boot**, **Google Gemini 1.5 Flash**, **React**, and a **Chrome Extension** that injects directly into Gmail.

---

## 🚀 Features

- ✅ Paste any email and generate an intelligent AI reply instantly
- ✅ Choose reply tone — **Professional**, **Casual**, or **Friendly**
- ✅ Copy generated reply to clipboard in one click
- ✅ Chrome Extension that injects an **"AI Reply"** button directly inside Gmail
- ✅ React web frontend for standalone use
- ✅ Spring Boot REST API backend powered by **Google Gemini 1.5 Flash**

---

## 🗂️ Project Structure

```
Email-Assistant/
├── email-writer-sb/          # Spring Boot Backend (Java)
├── email-writer-frontend/    # React Web Frontend
└── email-writer-ext/         # Chrome Extension
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Java, Spring Boot, Maven |
| AI Model | Google Gemini 1.5 Flash API |
| Frontend | React, Vite, JavaScript |
| Extension | Chrome Extension (Manifest V3) |
| HTTP Client | Spring WebClient |

---

## 📸 Screenshots

### 🌐 Web Frontend — Email Reply Generator
> Paste your email content, select a tone, and generate an AI reply instantly.

- Input: Original email content
- Tone selector: None / Professional / Casual / Friendly
- Output: AI-generated reply with Copy to Clipboard button

---

### 🔌 Chrome Extension — Gmail Integration
> The extension injects an **"AI Reply"** button directly next to the Gmail **"Send"** button inside the compose window.

![AI Reply button injected in Gmail compose window](screenshot-extension.png)

> One click on **"AI Reply"** reads the email thread and generates a smart reply using Gemini 1.5 Flash — without leaving Gmail!

---

## ⚙️ Setup & Installation

### Prerequisites
- Java 17+
- Node.js 18+
- Maven
- Google Gemini API Key ([Get one here](https://makersuite.google.com/app/apikey))
- Chrome Browser (for extension)

---

### 1️⃣ Backend — Spring Boot

```bash
cd email-writer-sb
```

Add your Gemini API key in `src/main/resources/application.properties`:

```properties
gemini.api.key=YOUR_GEMINI_API_KEY
gemini.api.url=https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent
```

Run the backend:

```bash
mvn spring-boot:run
```

Backend runs on: `http://localhost:8080`

---

### 2️⃣ Frontend — React Web App

```bash
cd email-writer-frontend
npm install
npm run dev
```

Frontend runs on: `http://localhost:5173`

---

### 3️⃣ Chrome Extension

1. Open Chrome and go to `chrome://extensions/`
2. Enable **Developer Mode** (toggle in top right)
3. Click **"Load unpacked"**
4. Select the `email-writer-ext/` folder
5. Open **Gmail** — you'll see an **"AI Reply"** button injected into the compose/reply window

> ⚠️ Make sure the Spring Boot backend is running on port `8080` before using the extension.

---

## 🔌 API Reference

### `POST /api/email/generate`

Generates an AI reply for the given email content.

**Request Body:**
```json
{
  "emailContent": "Hi, I wanted to follow up on our meeting...",
  "tone": "professional"
}
```

**Response:**
```json
{
  "reply": "Thank you for reaching out. I appreciate your follow-up..."
}
```

---

## 🔒 Environment Variables

Never hardcode your API key. Use `application.properties` or environment variables:

```properties
gemini.api.key=${GEMINI_API_KEY}
```

Set the environment variable before running:
```bash
# Windows
set GEMINI_API_KEY=your_api_key_here

# Linux/Mac
export GEMINI_API_KEY=your_api_key_here
```

---

## 📁 Key Files

| File | Description |
|------|-------------|
| `EmailGeneratorService.java` | Calls Gemini API and processes response |
| `WebClientConfig.java` | Configures Spring WebClient for HTTP calls |
| `application.properties` | App config and API key |
| `App.jsx` | Main React frontend component |
| `email-writer-ext/` | Chrome extension source files |

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first.

---

## 👨‍💻 Author

**Gopal Krishna**
- GitHub: [@gopalkrishna06114](https://github.com/gopalkrishna06114)
- LinkedIn: [Connect with me](https://www.linkedin.com/in/gopalkrishna06114)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
