# Whisper with a call_back function

A modified version of [OpenAI's Whisper](https://github.com/openai/whisper) — a general-purpose speech recognition model — with enhancements and custom features.

## 🔍 About

[Whisper](https://github.com/openai/whisper) is an automatic speech recognition (ASR) system trained on 680,000 hours of multilingual and multitask supervised data collected from the web.

This fork builds upon the original Whisper repository, adding:
- a call_back function to monitor the progress of audio processing

These changes make it easier to **know the progress of the file being processed**.

---

## 📦 Installation

### From Giyhub
```bash
pip install git+https://github.com/mkhadivi/whisper.git
```

## 🚀 Usage

Basic transcription example:
```bash
import whisper
model = whisper.load_model('large')

def progress_callback(progress, segment):#_value, progress_total):
    print(f"------------- Progress: {progress.n} of {progress.total} frames processed. ------------------")

audio = whisper.load_audio('<your_audip_file>')

result = model.transcribe(audio, verbose=False, progress_callback=progress_callback)
```
