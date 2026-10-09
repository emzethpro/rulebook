# Rulebook

Rulebook is a small browser tool that turns a collection of tweets into a clear writing style guide.

Upload a `.json`, `.txt`, or `.csv` file, or paste tweets directly into the app. Rulebook analyzes the writing and creates a rulebook covering sentence structure, rhythm, vocabulary, punctuation, tone, repeated phrases, and writing patterns.

## Features

- Upload or paste tweet collections
- Analyze large collections with chunked processing
- Choose an AI provider and model
- View the result as rendered content or raw Markdown
- Copy the result or download it as a `.md` file
- Works as a static HTML app in the browser

## Run locally

Open `index.html` in a modern web browser, or serve the folder with any simple local web server.

The app asks for an API key when you generate a rulebook. The key is used from your browser and is not included in this repository.

## Security note

This is a frontend-only application. API keys entered in the browser can be exposed to the browser, extensions, or network tools. For sensitive production use, place API requests behind your own secure backend.

## Files

- `index.html` — main Rulebook application
- `extractor.html` — style extraction version
- `fixed.html`, `gem.html`, `gpt.html`, and `threads.html` — additional provider or interface versions

## License

No license has been specified yet.
