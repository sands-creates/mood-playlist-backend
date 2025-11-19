# MoodMix – Backend 🎧

Node/Express backend API for a **mood-based playlist generator**.

The backend accepts a mood string from the React frontend, calls an external music API, and returns a normalized list of tracks for display.

---

## 🌐 Overview

The backend exposes a simple REST endpoint that the frontend calls:

- `GET /api/playlist?mood=<mood>`

It:

1. Reads the `mood` query parameter.
2. Validates / sanitizes the input.
3. Calls an external music API (for example, searching by mood / keywords).
4. Maps the raw API response into a clean, predictable JSON structure.
5. Returns that JSON to the frontend.

Example response shape:

```json
[
  {
    "title": "Song Title",
    "artist": "Artist Name",
    "albumArt": "https://image-url",
    "externalUrl": "https://open.music-service/track/123"
  }
]
