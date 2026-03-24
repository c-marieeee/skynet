# SkyNet Voice Assistant 🎙️🤖

A privacy-first, local voice assistant that combines speech recognition, local Large Language Models (LLMs), and text-to-speech. **SkyNet** listens for a wake word, processes your questions using **Ollama**, and speaks the answers back to you.

## 🚀 Features

* **Wake Word Activation:** Listens specifically for the "SkyNet" trigger.
* **100% Local Intelligence:** Uses the **Llama 3.2** model via Ollama—no data leaves your machine for processing.
* **Follow-up Mode:** Keeps the microphone active for 10 seconds after a response to allow for natural conversation.
* **Cross-Platform TTS:** Uses `pyttsx3` for offline text-to-speech that works on Windows, macOS, and Linux.

## 🛠️ Tech Stack

* **Language:** Python 3.x
* **STT (Speech-to-Text):** `SpeechRecognition` (Google Web Speech API)
* **LLM Engine:** [Ollama](https://ollama.com/) running `llama3.2:latest`
* **TTS (Text-to-Speech):** `pyttsx3`
* **API Interaction:** `requests` for local HTTP calls to Ollama

## 📥 Prerequisites

1.  **Install Ollama:** Download and install from [ollama.com](https://ollama.com).
2.  **Pull the Model:**
    Run the following command in your terminal:
    ```bash
    ollama run llama3.2
    ```
    
3.  **System Dependencies:** You may need to install `portaudio` on your system for PyAudio to work:
    * **macOS:** `brew install portaudio`
    * **Linux:** `sudo apt-get install python3-pyaudio`

## ⚙️ Installation & Setup

1. **Clone the Repository:**

```bash
git clone https://github.com/c-marieeee/assistant.git
cd assistant
```

2. **Install Python Dependencies:**

```bash
pip install -r requirements.txt
```

## 🖥️ Usage

1. **Start the Assistant:**

```bash
python stt.py
```

2. **Start the Assistant:**

* The terminal will show: `Listening for trigger word 'SkyNet'...`
* Say **"SkyNet"**.
* The assistant will respond: **"How can I help you?"**
* Ask your question (e.g., "What is the capital of France?" or "Tell me a joke.").
* SkyNet will process the response and speak it aloud.
* It will then wait **10 seconds** for a follow-up question before returning to the wake-word loop.

## 📂 Project Structure

* **`stt.py`** – Core logic including the voice loop, API calls to Ollama, and TTS.
* **`requirements.txt`** – Required libraries: `SpeechRecognition`, `pyaudio`, `requests`, and `pyttsx3`.

## 📝 Troubleshooting

* **Microphone Issues:** Ensure your default system microphone is set correctly in your OS settings.
* **API Error:** Make sure Ollama is running in the background (`ollama serve`).
* **JSON Errors:** This script handles Ollama's streaming JSON format. If you change models, ensure the model name in `stt.py` matches the one pulled in Ollama.
