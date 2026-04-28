# 🤖 AI Chatbot — Streamlit + LangChain + Ollama

A locally running conversational AI chatbot built with **Streamlit**, **LangChain**, and **Ollama**. The chatbot runs entirely on your machine — no API keys, no internet connection required after setup.

---

## 📸 Demo

> Chat with a local LLM (e.g., `llama3.2`) through a clean web UI with persistent conversation memory.

---

## 🚀 Features

- 💬 **Conversational Memory** — Keeps full chat history across the session
- 🧠 **System Prompt Support** — Pre-configured persona (e.g., "Act like an astronaut")
- 🌐 **Runs 100% Locally** — Powered by Ollama; no data leaves your machine
- ⚡ **Streamlit UI** — Clean, interactive browser-based chat interface
- 🔄 **LangChain Integration** — Uses `HumanMessage`, `AIMessage`, `SystemMessage` for structured message handling

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| [Streamlit](https://streamlit.io/) | Web UI framework |
| [LangChain](https://www.langchain.com/) | LLM orchestration & message handling |
| [Ollama](https://ollama.com/) | Local LLM runtime |
| [Llama 3.2](https://ollama.com/library/llama3.2) | Default language model |
| Python 3.10+ | Core language |

---

## 📦 Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
```

### 2. Install Python dependencies

```bash
pip install streamlit langchain-ollama langchain-core
```

### 3. Install Ollama & pull the model

Download Ollama from [https://ollama.com](https://ollama.com), then run:

```bash
ollama pull llama3.2
```

### 4. Run the app

```bash
streamlit run chatbot.py
```

Open your browser at `http://localhost:8501`

---

## 📁 Project Structure

```
📦 project-root
 ┣ 📄 chatbot.py       # Main Streamlit app
 ┗ 📄 README.md        # Project documentation
```

---

## ⚙️ Configuration

You can customize the chatbot behavior in `chatbot.py`:

```python
# Change the system persona
st.session_state.messages.append(SystemMessage("Act like a data scientist"))

# Change the model
llm = ChatOllama(model="llama3", temperature=1)
```

Available models (pull via `ollama pull <model>`):
- `llama3.2` *(default)*
- `llama3`
- `mistral`
- `gemma2`

---

## 🧠 How It Works

```
User types message
        ↓
Streamlit captures input
        ↓
Message added to session history (HumanMessage)
        ↓
Full history sent to ChatOllama via LangChain
        ↓
Model generates response (AIMessage)
        ↓
Response displayed in chat UI
```

---

## 📋 Requirements

- Python 3.10+
- Ollama installed and running locally
- At least 8GB RAM (for llama3.2)

---

## 🙌 Acknowledgements

- Inspired by [ThomasJanssen-tech/Ollama-Chatbot](https://github.com/ThomasJanssen-tech/Ollama-Chatbot)
- Built using LangChain's Ollama integration

---

## 📄 License

MIT License — feel free to use, modify, and share.
