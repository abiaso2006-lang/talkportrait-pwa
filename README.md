# TalkPortrait PWA

A small installable PWA shell for personal AI talking-avatar video generation.

## Important API note
Hugging Face Spaces do not share one standard endpoint or input schema. Open the target Space's API panel and set its endpoint name in the app. The current generic request sends two positional inputs in this order: image, audio. Change the `client.submit(...)` line if the Space expects another order or extra settings.

The prefilled URLs are placeholders, not verified working inference services. Replace them with actual public Gradio Spaces that support image + audio talking-head generation. A public Space can sleep, queue, change APIs, or be unavailable. Free service is not guaranteed.

## Files
- `index.html`: UI and application logic
- `manifest.json`: install metadata
- `sw.js`: offline shell cache
- `icon.svg`: app icon

## Host
GitHub Pages: create a repository, upload all four files to its root, then Settings → Pages → Deploy from a branch → main / root. Open the published HTTPS URL on Android Chrome.
Netlify: create a new site and upload the folder's files using Netlify Drop or connect the repository. Use the HTTPS URL.

## Install
Open the hosted HTTPS URL in Android Chrome → ⋮ → Add to Home screen / Install app.

## Limitations
- The app does not generate speech audio from typed text. Web Speech API is preview only; upload or record audio for actual lip-sync.
- Queue status and cancellation support vary by Gradio client and Space.
- Face quality checks are heuristic, not automatic face recognition.
- Captions/ffmpeg.wasm are intentionally omitted to keep mobile memory usage lower.
- Video output handling varies by Space and may need mapping changes.
