Overview
Graddio is a web-based voice AI application I built using Gradio for the UI and OpenAI's API for intelligent interactions. It transcribes user audio input to text (via Whisper), processes queries with GPT models for natural responses, and converts the AI's answers back to audio (via TTS). This creates a seamless, conversational voice assistant—perfect for demos, chatbots, or accessibility tools. The project highlights my experience with multimodal AI (audio/text), API orchestration, and rapid prototyping with Gradio, making it ideal for real-time web apps.

Note: Requires an OpenAI API key. For educational use; respect usage limits and privacy (e.g., don't store audio without consent).

Features
Speech-to-Text: Real-time transcription of user audio using OpenAI Whisper.
AI Conversation: GPT-powered responses to transcribed queries (e.g., chat-like Q&A).
Text-to-Speech: Converts AI answers to natural-sounding audio playback.
Gradio UI: Simple web interface for uploading/recording audio, viewing transcripts, and playing responses.
Configurable: Adjustable models (e.g., GPT-4o-mini for cost), voice styles, and response length.
Local Deployment: Runs on your machine with a shareable public URL for demos.
Tech Stack
Language: Python 3.9+
Key Libraries:
gradio for the web UI.
openai for Whisper transcription, GPT chat, and TTS.
ffmpeg for audio processing and format handling.
pydub for audio manipulation (if needed).
No external services beyond OpenAI; lightweight and self-contained.
Getting Started
Prerequisites
Python 3.9 or higher.
An OpenAI API key (get one at platform.openai.com).
FFmpeg installed (for audio encoding/decoding; see installation below).
Git for cloning.
Installation
Clone the repository:
bash
git clone https://github.com/abd0o0/graddio.git
cd graddio
Install Python dependencies:
bash
pip install -r requirements.txt
Install FFmpeg (required for audio handling):
Windows (via Chocolatey):
Install Chocolatey (run in PowerShell as admin):
text
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.WebClient]::new().DownloadString('https://chocolatey.org/install.ps1') | Invoke-Expression
Install FFmpeg:
text
choco install ffmpeg
Add FFmpeg to your PATH (restart terminal; verify with ffmpeg -version).
macOS:
text
brew install ffmpeg
Linux (Ubuntu/Debian):
text
sudo apt update && sudo apt install ffmpeg
Set up your OpenAI API key (create .env in the root):
text
OPENAI_API_KEY=your_openai_api_key_here
Usage
Run the application:
bash
python app.py  # Or main.py, depending on your entry script
Gradio will start a local server (e.g., http://127.0.0.1:7860).
Open the URL in your browser for the interactive UI.
Interact with the App:
Record or upload audio (e.g., "What's the weather today?").
The app transcribes it to text, generates a GPT response, and plays it back as audio.
View transcripts and responses in the interface.
CLI Quick Test (Optional):
bash
python test_audio.py --input recording.wav --output response.mp3
Transcribes input and generates audio output.
Examples and sample audio files are in the /examples folder. Customize models in app.py (e.g., gpt-4o-mini for faster/cheaper runs).
