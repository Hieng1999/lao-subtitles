# Lao Movie Subtitles · ຄຳບັນຍາຍພາສາລາວ

[![Website](https://img.shields.io/badge/Website-hieng1999.github.io%2Flao--subtitles-gold?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-blue?style=flat-square)](LICENSE)
[![GPU](https://img.shields.io/badge/Accelerated-NVIDIA%20RTX%205090-76B900?style=flat-square&logo=nvidia)](https://github.com/Hieng1999/lao-subtitles)
[![Model](https://img.shields.io/badge/Fine--Tuned-NLLB--200%20%2B%20LoRA-orange?style=flat-square)](https://github.com/Hieng1999/lao-subtitles)

High-quality Lao-language subtitle files (`.srt`) for legendary films that have **no Lao subtitles available anywhere else online**.

🌐 **Browse, search & download directly at the live website → [hieng1999.github.io/lao-subtitles](https://hieng1999.github.io/lao-subtitles/)**

Major subtitle platforms (OpenSubtitles, Subscene, Addic7ed) do not support Lao as a language category or upload format. This open-source repository fills that gap so Lao speakers and families worldwide can enjoy world-class movies in their own language. Everything here is **free to download**.

---

## 🎬 Available Subtitles

| Movie | Year | Genre | IMDb | Subtitle File | Translation Quality & Status |
|:---|:---:|:---:|:---:|:---|:---|
| **The Shawshank Redemption** | 1994 | Drama / Crime | [tt0111161](https://www.imdb.com/title/tt0111161/) | [`subtitles/The.Shawshank.Redemption.1994.lao.srt`](subtitles/The.Shawshank.Redemption.1994.lao.srt) | ✓ LoRA fine-tuned on RTX 5090 |
| **Coco** | 2017 | Animation / Family | [tt2380307](https://www.imdb.com/title/tt2380307/) | [`subtitles/Coco.2017.lao.srt`](subtitles/Coco.2017.lao.srt) | ✓ LoRA fine-tuned on RTX 5090 |
| **Moana** | 2016 | Animation / Adventure | [tt3521164](https://www.imdb.com/title/tt3521164/) | [`subtitles/Moana.2016.lao.srt`](subtitles/Moana.2016.lao.srt) | ✓ LoRA fine-tuned on RTX 5090 |
| **Frozen** | 2013 | Animation / Fantasy | [tt2294629](https://www.imdb.com/title/tt2294629/) | [`subtitles/Frozen.2013.lao.srt`](subtitles/Frozen.2013.lao.srt) | ✓ LoRA fine-tuned on RTX 5090 |
| **Blood Diamond** | 2006 | Action / Drama | [tt0450259](https://www.imdb.com/title/tt0450259/) | [`subtitles/Blood.Diamond.2006.lao.srt`](subtitles/Blood.Diamond.2006.lao.srt) | ✓ LoRA fine-tuned on RTX 5090 |

*More classics and modern hits in progress. Requests are welcome via GitHub Issues.*

---

## 🧠 How These Subtitles Are Produced

These subtitles are produced using an advanced local AI translation pipeline running 100% offline on an **NVIDIA GeForce RTX 5090 (32GB VRAM)**:

1. **PacTranz 5-Step Cinema Methodology**:
   - **Step 1: Named Entity Recognition & Cultural Pronouns** — Enforces natural honorifics (`ເຈົ້າ`, `ຂ້ອຍ`, `ອ້າຍ`, `ເອື້ອຍ`, `ນ້ອງ`) matched to character relationships.
   - **Step 2: Literal Draft Generation** — Translates dialogue while preserving dramatic tone and pacing.
   - **Step 3: Lao Syntax Alignment** — Normalizes word order, applies correct classifiers (`ໂຕ`, `ຄົນ`, `ຫົວ`, `ຄັນ`), and aligns serial verb constructions (`ເອົາມາ`, `ແລ່ນໜີ`).
   - **Step 4: Spoken Dialogue & Diglossia Pass** — Converts formal written Lao into natural spoken speech (*Phasa Pak*) with authentic pragmatic particles (`ເດີ້`, `ເນາະ`, `ແດ່`, `ແມ`).
   - **Step 5: Automated QA & Linguistic Audit** — Quality checks via chrF++ scoring and the **Pamela Sue Wright Linguistic Audit** (checking against 50,210 Lao dictionary terms, tone mark stacking, and eliminating Thai loanword drift).

2. **Fine-Tuned Neural Adapter (LoRA)**:
   - Built on Meta's NLLB-200 architecture.
   - Fine-tuned on **218,784 parallel sentence pairs** including 30,400 linguistic stress tests (Winograd Schema, homonym disambiguation, cultural idioms) achieving an **88.33 / 100 chrF++ quality score**.

3. **Frame-Accurate Subtitle Timing**:
   - Audio-aligned with popular release rips (BluRay / BrRip / Sparks / YIFY) with frame-accurate millisecond timestamps.

---

## 📺 How to Use

1. **Download**: Click any `.srt` link above or download from the [website](https://hieng1999.github.io/lao-subtitles/).
2. **Rename**: Rename the `.srt` file to match the exact filename of your movie video file:
   ```
   Coco.2017.720p.mkv
   Coco.2017.720p.srt
   ```
3. **Play**: Open the video in **VLC**, **MPV**, **Plex**, **IINA**, or **PotPlayer** — the Lao subtitles will automatically appear!
4. **Timing Nudge**: If your release has different opening logos, adjust subtitle delay in VLC by pressing `G` (earlier) or `H` (later).

---

## 🤝 Contributing & Corrections

Native Lao speakers: corrections and feedback are warmly welcomed!
- Open an **[Issue](https://github.com/Hieng1999/lao-subtitles/issues)** with the movie name, timestamp, and suggested Lao correction.
- Send a **Pull Request** directly with your edits. Corrections feed back into our local AI training memory.

---

## ❤️ About This Project

This started with a simple wish: to help someone I love enjoy movies in the language they're most comfortable in. Lao subtitles for major films basically don't exist online — so I built a translation pipeline and started making them, and I'm sharing the results here free for anyone to use. If they help even one more family enjoy a movie together, it's worth it.

---

## 📜 License & Disclaimer

Fan-made subtitle translations, shared freely for educational and accessibility purposes. The underlying films and their original dialogue remain © their respective rights holders; this project claims no ownership over the original source media.
