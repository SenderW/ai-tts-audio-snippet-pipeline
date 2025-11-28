# AI TTS Audio Snippet Pipeline

Small Flask app that uses OpenAI text to speech to insert spoken snippets into an existing MP3 file. Typical use cases are automatic intros, mid roll calls to action, and outros for podcasts, promos, or training audio.

## What this tool does

- Accepts an uploaded audio file (for example MP3).
- Accepts at least four text lines:
  - Intro
  - First mid roll
  - Second mid roll
  - Outro
- Uses OpenAI text to speech to generate four short speech snippets.
- Inserts these snippets into the audio:
  - Intro before the track
  - First mid roll after the first quarter
  - Second mid roll after the second quarter
  - Outro at the end
- Exports a new MP3 file with simple ID3 metadata.

This is a compact example of AI driven content automation for audio production.

## Architecture

- **Framework**: Flask
- **Audio processing**: pydub
- **Metadata**: mutagen
- **Text to speech**: OpenAI Audio API (`client.audio.speech.create` with `gpt-4o-mini-tts` or similar)

## Setup

1. Clone the repository

```bash
git clone https://github.com/your-account/ai-tts-audio-snippet-pipeline.git
cd ai-tts-audio-snippet-pipeline
