# AI TTS Audio Snippet Pipeline

Small Flask app that uses OpenAI text to speech to insert spoken snippets into existing MP3 files. It is meant as a simple example for AI based content automation for podcasts, marketing audio or training material.

## What this tool does

- Accepts an uploaded MP3 file.
- Accepts at least four text lines:
  - Intro
  - First mid roll
  - Second mid roll
  - Outro
- Uses OpenAI text to speech to generate four speech snippets.
- Inserts these snippets into the track at fixed positions:
  - Intro before the original audio
  - First mid roll after the first quarter
  - Second mid roll after the second quarter
  - Outro at the end
- Exports a new MP3 file and writes simple ID3 metadata.

## Architecture

- Framework: Flask
- Audio processing: pydub
- Metadata: mutagen
- Text to speech: OpenAI Audio API (`client.audio.speech.create` with `gpt-4o-mini-tts` or similar model)

## Setup

1. Clone the repository

```bash
git clone https://github.com/your-account/ai-tts-audio-snippet-pipeline.git
cd ai-tts-audio-snippet-pipeline
