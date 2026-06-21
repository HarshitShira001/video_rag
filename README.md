# 🎬 video_rag

An AI-powered meeting intelligence tool built with **Streamlit** and **LangChain**. It transcribes YouTube URLs or local media, extracts summaries, action items, decisions, and builds a **RAG Chat** over the transcript.

---

## ✨ Features
*   **🔊 Audio Processing:** Downloads YouTube audio or converts local formats to WAV.
*   **📝 Dual Transcription:** Local OpenAI Whisper (English) or Sarvam AI API (Hinglish).
*   **📊 Insight Extraction:** Auto-extracts summaries, action items, decisions, and questions using Mistral AI.
*   **💬 RAG Chat:** Chat interactive UI powered by ChromaDB & Mistral AI.

---

## 🗂️ Project Structure
```
rag_video/
├── app.py                   # Streamlit Frontend & Orchestrator
├── core/
│   ├── transcriber.py       # Whisper / Sarvam transcription
│   ├── summarizer.py        # Map-Reduce summary & title generation
│   ├── extractor.py         # Decisions & action items extractor
│   ├── vector_store.py      # ChromaDB document indexing
│   └── rag_engine.py        # LangChain LCEL RAG chain
└── utils/
    └── audio_processor.py   # Audio acquisition, download & chunking
```

---

## ⚙️ Setup & Execution

### 1. Install System Dependency
Ensure you have [FFmpeg](https://ffmpeg.org/) installed and added to your system environment variables.

### 2. Install Python Packages
```bash
pip install -r Requirements.txt
```

### 3. Add API Keys
Create a `.env` file in the root folder:
```env
MISTRAL_API_KEY=your_mistral_api_key
SARVAM_API_KEY=your_sarvam_api_key (optional, for Hinglish support)
```

### 4. Run the Web App
```bash
streamlit run app.py
```

---

## 🛠️ How to Use
1. Paste a YouTube URL or a local file path (e.g. `.mp4`, `.mp3`) in the sidebar.
2. Select the input language (English or Hinglish).
3. Click **⚡ Analyse** to run the processing pipeline.
4. Once completed, view the summary insights and use the chat input at the bottom to query the transcript context.
