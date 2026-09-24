# Voice Assistant

**Desktop app (CLI)** — offline voice-controlled automation assistant ("Ultra Advanced AI Assistant", 500+ tasks: files, system control, automation). No LLM, no API keys.

## Run

```bash
python voice_assistant.py     # voice mode on a desktop with mic + speaker
```

On machines without a microphone (e.g. headless servers) it falls back to typed input automatically.

## Deps

```bash
pip install pyautogui SpeechRecognition pyttsx3 keyboard pyperclip psutil opencv-python pillow numpy requests
```

(`pyaudio` needed for real mic input; `winshell` is Windows-only and optional.)

## Notes

- Mic (PyAudio) and speaker (eSpeak on Linux) paths need real audio hardware — cannot be verified headless. Boot + text-input fallback verified under `xvfb-run`.
- Fixed 2026-09-24: `winshell` import is Windows-only (optional), TTS engine failure degrades to text output, missing mic falls back to typed input.
- Windows COM features (recycle-bin empty etc.) only run on Windows.
