# Deepdub API Documentation

Developer documentation for [Deepdub](https://deepdub.com) voice AI APIs. Built with [Mintlify](https://mintlify.com).

**Docs site:** [docs.deepdub.com](https://docs.deepdub.com)

## APIs

| API | Protocol | Description |
|-----|----------|-------------|
| [REST TTS](/api-reference/tts/generate-and-stream-tts-audio) | HTTP POST | Generate a complete audio file from text |
| [WebSocket TTS](/api-reference/websocket/overview) | WebSocket | Stream audio chunks in real-time for low-latency playback |
| [Gender Detection](/api-reference/gender-detection/classify-speaker-gender) | HTTP POST | Classify speaker gender from audio |
| [Voice Management](/api-reference/voice/get-voice-prompts) | HTTP REST | Upload, list, update, and delete voice prompts |

## Supported output formats

| Format | REST API | WebSocket API | Description |
|--------|----------|---------------|-------------|
| `mp3` | Complete MP3 file | MP3 chunks | Compressed, smallest size. **Default.** |
| `wav` | Complete WAV file with headers | Raw PCM bytes (headerless) | Uncompressed audio |
| `opus` | Complete Opus file | Opus chunks | High-quality compressed, efficient for streaming |
| `mulaw` | µ-law encoded file | µ-law chunks | 8-bit telephony encoding |

> **Note:** The WebSocket `wav` format returns **headerless raw PCM bytes** — no WAV file header is included. For the REST API, a complete WAV file with headers is returned.

## Supported sample rates

| Sample rate | Description |
|-------------|-------------|
| `8000` | Telephony (µ-law) |
| `16000` | Wideband speech |
| `22050` | Standard quality |
| `24000` | Enhanced speech |
| `32000` | High quality |
| `36000` | Studio speech |
| `44100` | CD quality |
| `48000` | Professional audio |

## SDKs

| SDK | Install | Docs |
|-----|---------|------|
| Python | `pip install deepdub` | [Python SDK](/sdk) |
| JavaScript / Node.js | `npm install @deepdub/node` | [JavaScript SDK](/sdk-javascript) |

## Free trial

Use the free trial API key to get started — no sign-up required:

```
dd-00000000000000000000000065c9cbfe
```

## Local development

Install the [Mintlify CLI](https://www.npmjs.com/package/mintlify) to preview docs locally:

```bash
npm i -g mintlify
mintlify dev
```

Changes pushed to `main` are deployed automatically.
