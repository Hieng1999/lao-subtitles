# Lao Movie Subtitles · ຄຳບັນຍາຍພາສາລາວ

Lao-language subtitle files (`.srt`) for films that have **no Lao subtitles available anywhere**.

Major subtitle sites (OpenSubtitles, etc.) do not support Lao as a language at all — there is no
Lao category to search or upload to. This repository exists to fill that gap so Lao speakers can
watch these films with subtitles in their own language.

## ⚠️ AI-assisted translations

These subtitles are produced with a machine-translation pipeline (Google **Gemini** + Meta **NLLB**,
with a curated glossary and per-character pronoun rules), then reviewed. They are **not** professional
human translations. Corrections are welcome — please open an issue or a pull request.

## Available subtitles

| Movie | Year | IMDb | File | Status |
|---|---|---|---|---|
| Frozen | 2013 | tt2294629 | `subtitles/Frozen.2013.lao.srt` | ✓ reviewed, watch-ready |
| Moana | 2016 | tt3521164 | `subtitles/Moana.2016.lao.srt` | ✓ reviewed, watch-ready |
| Blood Diamond | 2006 | tt0450259 | _pending_ | ⏳ re-translation in progress |

## How to use

1. Download the `.srt` for your movie from the `subtitles/` folder.
2. Rename it to match your video file (keep `.srt`), or load it manually in your player (VLC, MPV, Plex).
3. If timing is off, your video is a different release — nudge the subtitle delay, or open an issue.

## Contributing / corrections

Native Lao speakers: fixes are hugely appreciated. Open an issue (movie + line number + correct Lao)
or send a pull request. Corrections also feed back into the translation glossary.

## License / disclaimer

Fan-made subtitle translations, shared freely for accessibility. The underlying films and their
original dialogue are © their respective rights holders; this project claims no ownership.