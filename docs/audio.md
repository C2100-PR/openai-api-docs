# Audio API

The Audio API provides speech-to-text (transcription) and text-to-speech capabilities.

## Text to Speech

```bash
curl https://api.openai.com/v1/audio/speech \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "tts-1",
    "input": "The quick brown fox jumped over the lazy dog.",
    "voice": "alloy"
  }' \
  --output speech.mp3
```

### Available Voices
- alloy
- ash
- coral
- echo
- fable
- onyx
- nova
- shimmer

## Speech to Text (Transcription)

```bash
curl https://api.openai.com/v1/audio/transcriptions \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: multipart/form-data" \
  -F file="@/path/to/file/audio.mp3" \
  -F model="whisper-1"
```

### Supported Audio Formats
- flac
- mp3
- mp4
- mpeg
- mpga
- m4a
- ogg
- wav
- webm

## Translation

Translate audio directly to English:

```bash
curl https://api.openai.com/v1/audio/translations \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: multipart/form-data" \
  -F file="@/path/to/file/german.m4a" \
  -F model="whisper-1"
```