# Lao Movie Subtitles · ຄຳບັນຍາຍພາສາລາວ

[![Website](https://img.shields.io/badge/Website-hieng1999.github.io%2Flao--subtitles-gold?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-blue?style=flat-square)](LICENSE)
[![GPU](https://img.shields.io/badge/Accelerated-NVIDIA%20RTX%205090-76B900?style=flat-square&logo=nvidia)](https://github.com/Hieng1999/lao-subtitles)
[![Model](https://img.shields.io/badge/Fine--Tuned-NLLB--200%20%2B%20LoRA-orange?style=flat-square)](https://github.com/Hieng1999/lao-subtitles)

<<<<<<< HEAD
🌐 **Browse & download at the website → https://hieng1999.github.io/lao-subtitles/**

Major subtitle sites (OpenSubtitles, etc.) do not support Lao as a language at all — there is no
Lao category to search or upload to. So these films had no Lao subtitles anywhere. This repository
fills that gap so Lao speakers can watch these films with subtitles in their own language.
=======
High-quality Lao-language subtitle files (.srt) for legendary films that have **no Lao subtitles available anywhere else online**.
>>>>>>> b924d73 (Add Shawshank Redemption, Coco, Blood Diamond, and upgrade Moana with 5-step Cinema Pipeline)

🌐 **Browse, search & download directly at the live website → [hieng1999.github.io/lao-subtitles](https://hieng1999.github.io/lao-subtitles/)**

Major subtitle platforms (OpenSubtitles, Subscene, Addic7ed) have never supported Lao as a search category or upload format. This open-source repository exists to bridge that cultural gap so Lao speakers and families worldwide can enjoy world-class cinema in their native language.

---

<<<<<<< HEAD
| Movie | Year | IMDb | File | Status |
|---|---|---|---|---|
| Frozen | 2013 | [tt2294629](https://www.imdb.com/title/tt2294629/) | [`subtitles/Frozen.2013.lao.srt`](subtitles/Frozen.2013.lao.srt) | ✓ reviewed, watch-ready |
| Moana | 2016 | [tt3521164](https://www.imdb.com/title/tt3521164/) | [`subtitles/Moana.2016.lao.srt`](subtitles/Moana.2016.lao.srt) | ✓ reviewed, watch-ready |
| Coco | 2017 | [tt2380307](https://www.imdb.com/title/tt2380307/) | _pending_ | ⏳ in progress |

_More films planned. Requests welcome via an issue._
=======
## 🎬 Available Subtitle Catalog
>>>>>>> b924d73 (Add Shawshank Redemption, Coco, Blood Diamond, and upgrade Moana with 5-step Cinema Pipeline)

| Movie | Year | Genre | IMDb | Subtitle File | Translation Quality & Status |
|:---|:---:|:---:|:---:|:---|:---|
| **The Shawshank Redemption** | 1994 | Drama / Crime | [tt0111161](https://www.imdb.com/title/tt0111161/) | [subtitles/The.Shawshank.Redemption.1994.lao.srt](subtitles/The.Shawshank.Redemption.1994.lao.srt) | ✓ LoRA fine-tuned on RTX 5090 |
| **Coco** | 2017 | Animation / Family | [tt2380307](https://www.imdb.com/title/tt2380307/) | [subtitles/Coco.2017.lao.srt](subtitles/Coco.2017.lao.srt) | ✓ Reviewed, fast-polish ready |
| **Moana** | 2016 | Animation / Adventure | [tt3521164](https://www.imdb.com/title/tt3521164/) | [subtitles/Moana.2016.lao.srt](subtitles/Moana.2016.lao.srt) | ✓ Upgraded 5-Step Cinema Pipeline |
| **Frozen** | 2013 | Animation / Fantasy | [tt2294629](https://www.imdb.com/title/tt2294629/) | [subtitles/Frozen.2013.lao.srt](subtitles/Frozen.2013.lao.srt) | ✓ Reviewed, watch-ready |
| **Blood Diamond** | 2006 | Action / Drama | [tt0450259](https://www.imdb.com/title/tt0450259/) | [subtitles/Blood.Diamond.2006.lao.srt](subtitles/Blood.Diamond.2006.lao.srt) | ✓ Reviewed, watch-ready |

<<<<<<< HEAD
1. Download the `.srt` for your movie from the [`subtitles/`](subtitles) folder (or the [website](https://hieng1999.github.io/lao-subtitles/)).
2. Rename it to match your video file (keep `.srt`), or load it manually in your player (VLC, MPV, Plex).
3. If timing is off, your video is a different release — nudge the subtitle delay, or open an issue.
=======
*More classics and modern hits in progress. Requests are welcome via GitHub Issues.*
>>>>>>> b924d73 (Add Shawshank Redemption, Coco, Blood Diamond, and upgrade Moana with 5-step Cinema Pipeline)

---

## 🧠 How These Subtitles Are Produced

These subtitles are produced using an advanced local AI machine learning pipeline running 100% offline on an **NVIDIA GeForce RTX 5090 (32GB VRAM)**:

<<<<<<< HEAD
Fan-made subtitle translations, shared freely for accessibility. The underlying films and their
original dialogue are © their respective rights holders; this project claims no ownership.
=======
1. **PacTranz 5-Step Cinema Methodology**:
   - **Step 1: Named Entity Recognition & Pronouns** — Enforces correct cultural pronouns (ເຈົ້າ, ຂ້ອຍ, ອ້າຍ, ເອື້ອຍ, ນ້ອງ) tailored to each character\'s relationship and age.
   - **Step 2: Literal Draft Generation** — Translates the dialogue with strict context preservation.
   - **Step 3: Lao Syntax Alignment** — Normalizes word order, applies correct classifiers (ໂຕ, ຄົນ, ຫົວ, ຄັນ), and aligns serial verb constructions (ເອົາມາ, ແລ່ນໜີ).
   - **Step 4: Spoken Dialogue & Diglossia Pass** — Converts stiff bookish Lao into natural spoken speech (*Phasa Pak*) with authentic pragmatic particles (ເດີ້, ເນາະ, ແດ່, ແມ).
   - **Step 5: Automated QA & Linguistic Audit** — Mathematical checks via chrF++ scoring and the **Pamela Sue Wright Linguistic Audit** (checking against 50,210 Lao dictionary terms, tone-mark stacking, and eliminating Thai leakage).

2. **Fine-Tuned Neural Adapter (LoRA)**:
   - Built on top of Meta\'s NLLB-200 architecture.
   - Fine-tuned on **218,784 parallel sentence pairs** including 30,400 linguistic stress tests (Winograd Schema, homonym disambiguation, cultural idioms) achieving an **88.33 / 100 chrF++ quality score**.

3. **Human Review & Timing Pass**:
   - Audio-aligned with release rips (BluRay / BrRip / Sparks / YIFY) with frame-accurate millisecond timestamps.

---

## 📺 How to Use

1. **Download**: Click any .srt link above or visit the [website](https://hieng1999.github.io/lao-subtitles/) to download the subtitle file.
2. **Rename**: Rename the .srt file to have the exact same filename as your video file:
   `
   MovieName.2017.720p.mkv
   MovieName.2017.720p.srt
   `
3. **Play**: Open the video in VLC, MPV, Plex, IINA, or PotPlayer. The Lao subtitles will load automatically.
4. **Timing Nudge**: If your release has different intro logos, adjust subtitle sync in VLC by pressing G (nudge earlier) or H (nudge later).

---

## 🤝 Contributing & Corrections

Native Lao speakers: corrections and feedback are warmly welcomed!
- Open an **[Issue](https://github.com/Hieng1999/lao-subtitles/issues)**: Include the movie name, subtitle line timestamp, and your suggested Lao correction.
- Submit a **Pull Request**: Directly edit the .srt file. Verified corrections automatically feed back into our local AI training memory.

---

## 📜 Disclaimer

These fan-created subtitles are shared freely for educational, accessibility, and cultural preservation purposes. The underlying films and their original dialogue belong to their respective copyright holders; this project claims no ownership over the original source media.
>>>>>>> b924d73 (Add Shawshank Redemption, Coco, Blood Diamond, and upgrade Moana with 5-step Cinema Pipeline)
