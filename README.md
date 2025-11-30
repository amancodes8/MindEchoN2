# 🧠 MindEcho — AI-Powered Emotional Wellbeing Companion

> **Multi-User Video Calling • Real-time Emotion Sensing • Voice Chat • Multilingual • Data Storage**
>
> *Built for Google Gemini + Lingo.dev Partner Tracks*

---

## 🌟 Overview

**MindEcho** is an AI-driven mental wellbeing companion that blends **multi-user video calling**, real-time emotional sensing, multilingual AI conversations, and smart wellbeing tools into a single seamless experience.

The project uses:
* **Google Gemini 2.5 Flash** for smart, empathetic AI conversations.
* **Lingo.dev** for multilingual translation and tone-preserving localization.
* **WebRTC & Socket.io and Agora** for real-time video and audio communication.
* **MongoDB** for secure user data and session persistence.
* **Face Emotion Tracking** for non-verbal emotional cues.

All processing is **privacy-first**, and emotion detection runs locally on the user's device.

---

## 🚀 Features

### 📞 Multi-User Video Calling (New!)
* **Real-time WebRTC:** Enables secure, low-latency group video calls.
* **Agora:** Handles connection management and real-time status updates.
* **Use Case:** Perfect for peer support groups or remote therapy sessions.

### 💾 Data Persistence
* **MongoDB Integration:** User profiles, emotional logs, and conversation history are securely stored.
* **Session Tracking:** Resume your progress and view historical mood trends.

### 🎤 Voice-Based AI Chat
* **Hold-to-talk microphone** for natural interaction.
* **Pipeline:** Audio → STT → Gemini processing → Reply.
* **Real-time** natural conversation flow.

### 🏷 Tone Selector
Switch the AI assistant’s personality instantly:
| Mode | Description |
| :--- | :--- |
| **🌿 Calm** | Soft, slow, reassuring. |
| **⚡ Motivation** | Energetic, uplifting. |
| **🧘 Grounding** | Simple, stabilizing tips. |

### 🌍 Multilingual Support (Lingo.dev Partner Track)
* **Auto language detection.**
* **Pipeline:** User speech → Lingo.dev → English → Gemini → Lingo.dev → User’s language.
* **Tone Preservation:** Maintains the emotional "vibe" across translations.

### 📷 Real-time Facial Emotion Tracking
* Runs fully locally in the browser using `face-api.js`.
* **Metrics:** Calculates Calm / Focus / Tension scores.
* **Privacy:** No camera frames are ever uploaded.

---

## 🤝 Partner Tracks Used

### 🟧 Google Gemini Track
We utilize the **Google Generative AI SDK** for:
* **Gemini 2.5 Flash Model:** Core reasoning and conversational agent.
* **Speech-to-Text:** Processing user voice input.
* **Contextual Awareness:** Determining when to trigger wellness tools.

### 🟪 Lingo.dev Track
We use the **Lingo.dev SDK** for:
* **Localization:** Auto-translation of inputs and outputs.
* **Tone Consistency:** Ensuring the "Calm" or "Motivated" persona survives translation, a key requirement for mental health apps.

---

## 🛠 Tech Stack

### Frontend
* **React (Vite):** Fast, modern UI framework.
* **TailwindCSS:** Styling and layout.
* **WebRTC:** Peer-to-peer video calling.
* **face-api.js:** Local client-side AI for emotion detection.

### Backend
* **Node.js + Express:** Server API.
* **Socket.io:** Real-time signaling for video and chat.
* **MongoDB:** Database for persistent storage.
* **Google Generative AI SDK:** AI Model integration.
* **Lingo.dev SDK:** Translation services.

---

## 📦 Installation & Setup

You need to clone **two separate repositories** (Frontend & Backend) and run them concurrently.

### 1️⃣ Backend Setup (echobackend)

1.  **Clone the Backend:**
    ```bash
    git clone [https://github.com/amancodes8/echobackend](https://github.com/amancodes8/echobackend)
    cd echobackend
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Create `.env` file:**
    Create a file named `.env` in the `echobackend` directory and add:
    ```env
    PORT=4000
    MONGODB_URI=your_mongodb_connection_string_here
    GEMINI_API_KEY=your_gemini_key_here
    LINGODOTDEV_API_KEY=your_lingo_dev_key_here
    ```
    *(Replace placeholder values with your actual API keys and Mongo connection string).*

4.  **Start Backend Server:**
    ```bash
    npm start
    ```
    *The backend (API & Socket.io) will run at: `http://localhost:4000`*

### 2️⃣ Frontend Setup (mindechofrontend)

1.  **Clone the Frontend:**
    ```bash
    git clone [https://github.com/amancodes8/mindechofrontend](https://github.com/amancodes8/mindechofrontend)
    cd mindechofrontend
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Create `.env` file:**
    Create a file named `.env` in the `mindechofrontend` directory and add:
    ```env
    VITE_BACKEND_URL=http://localhost:4000
    ```

4.  **Run Frontend App:**
    ```bash
    npm run dev
    ```
    *The frontend will run at: `http://localhost:5173`*

---

## ▶️ Usage Guide

1.  **Start Both Servers:**
    Ensure both the backend (`localhost:4000`) and the frontend (`localhost:5173`) are running in separate terminals.

2.  **Dashboard & Tracking:**
    Open `http://localhost:5173`. The dashboard shows emotion metrics. Click "Start" on the Camera panel to begin local emotion tracking.

3.  **Use ChatBot:**
    Click the floating chat bubble. Choose a tone (Calm/Motivation), hold the mic, and speak. The AI will respond with audio and text.

4.  **Start a Video Call:**
    Navigate to the **'Call'** section. Create or join a room ID to initiate a secure multi-user video session using WebRTC.

---

## 🔒 Privacy Notes

* **Camera Data:** Processed 100% locally in the browser via `face-api.js`. No images are sent to the server.
* **Video Calls:** Utilize peer-to-peer (P2P) WebRTC connections where possible for maximum security.
* **Data Storage:** All sensitive data (user logs, session history) is saved securely in your private MongoDB instance.

---

## 🏁 Final Notes
This project is a submission for the **Google Gemini** and **Lingo.dev** hackathon tracks. It demonstrates how multimodal AI and real-time communication can create a supportive, accessible mental health tool.
