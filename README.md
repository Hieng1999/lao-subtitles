# Lao Movie Subtitles · ຄຳບັນຍາຍພາສາລາວ

[![Website](https://img.shields.io/badge/Website-hieng1999.github.io%2Flao--subtitles-gold?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![Movies](https://img.shields.io/badge/Catalog-287%20Movies-blue?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![Cues](https://img.shields.io/badge/Cues-238,841%20Localized-green?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![Verified Corrections](https://img.shields.io/badge/Verified%20Corrections-7,266-brightgreen?style=flat-square)](https://github.com/Hieng1999/lao-subtitles#-how-we-verify-quality)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-blue?style=flat-square)](LICENSE)
[![GPU](https://img.shields.io/badge/Accelerated-NVIDIA%20RTX%205090-76B900?style=flat-square&logo=nvidia)](https://github.com/Hieng1999/lao-subtitles)
[![Model](https://img.shields.io/badge/Fine--Tuned-NLLB--200%20(1.3B)%20%2B%20LoRA-orange?style=flat-square)](https://github.com/Hieng1999/lao-subtitles)

High-quality Lao-language subtitle files (`.srt`) for **287 legendary films** that have **no Lao subtitles available anywhere else online**. Over **238,841 dialogue cues** localized into authentic, natural spoken Lao.

🌐 **Browse, search & download directly at the live website → [hieng1999.github.io/lao-subtitles](https://hieng1999.github.io/lao-subtitles/)**

Major subtitle platforms (OpenSubtitles, Subscene, Addic7ed) do not support Lao as a language category or upload format. This open-source repository fills that gap so Lao speakers and families worldwide can enjoy world-class movies in their own language. Everything here is **free to download**.

---

## 🏆 How We Verify Quality

Every one of the 287 movies in this catalog has been **independently re-checked, cue by cue, against its original English source** — not just translated once and published. Here's exactly what that means, in real numbers from the actual verification run (not estimates):

| Verification Step | Result |
|:---|---:|
| Movies re-verified cue-by-cue | **287 / 287** |
| Total dialogue cues checked | **238,751** |
| Cues where re-translation disagreed with the published line | 220,361 |
| Rejected — known decoder artifact (garbled token) | 14,344 |
| Rejected — hallucinated word substitution | 5,091 |
| Rejected — stutter/repetition artifact | 4,874 |
| Rejected — untranslated English left in the Lao text | 7,817 |
| Sent to the English-only semantic-equivalence judge | 31,338 |
| Rejected — judge could not confirm the meaning matched | 23,278 |
| **Corrections actually applied (passed every check)** | **7,266** |

**How a correction gets approved — the "double lock":** a candidate replacement only ever gets written to a published `.srt` file if it passes **both** of these, independently:

1. **Deterministic Lao-text filters** — reject anything matching a known decoder failure mode we found and catalogued by hand: a garbled placeholder token, a real word ("cat", "interfere") standing in for a slang term it shouldn't, an immediately-repeated stutter, or English words left untranslated inside the Lao line.
2. **English-only back-translation judge** — the candidate Lao line is translated *back* into English with a separate reverse-direction model, and a local LLM judge is asked only "do these two English sentences mean the same thing?" — it never reads Lao, so it can't be fooled by fluent-looking-but-wrong Lao text.

A correction is applied only if **both** locks agree. If either one is unsure, the line is left as published and nothing changes.

> **We're not claiming this is perfect.** Some known failure patterns — like a specific word the model occasionally substitutes for slang or profanity it doesn't have a good translation for — are hard to fully eliminate through re-translation alone, and a small number of these remain in the catalog even after this process (see **Contributing & Corrections** below for how to report one). We'd rather tell you that honestly than publish a big round number that doesn't hold up.

> 📈 **Round-trip fidelity benchmark (in progress, updates automatically):** 200/287 movies scored so far, running average **chrF++ 60.8** / **BLEU 45.5** (published Lao translated back to English and compared to the original — see the per-movie ↺ scores below). See **[Model Evolution](https://hieng1999.github.io/lao-subtitles/#model-evolution)** on the live site for how this compares across model generations.

---

## 📊 Model Translation Quality Benchmarks

These are real, independently-computable numbers — a fresh [sacrebleu](https://github.com/mjpost/sacrebleu) `chrF++`/`BLEU`/`TER` run (audited 2026-09-14 14:40:40) against 100 human-reference translation pairs per domain, re-generated every time this catalog is published, not hand-maintained or estimated:

| Benchmark Domain | Focus | chrF++ | BLEU | TER (lower=better) |
|:---|:---|:---:|:---:|:---:|
| **False Friends Cognate Challenge** | Hard-Negative Lao-Thai Cognates (100 pairs) | **58.1** | **63.8** | **48.8%** |
| **SEA-HELM Cultural & Regional** | Regional Culture & Geography (100 pairs) | **48.8** | **58.5** | **57.6%** |
| **Tatoeba Spoken Conversational** | Natural Conversational Dialogues (100 pairs) | **49.8** | **63.3** | **52.0%** |
| **Tennessee Civics & Legal** | Legal & Government Statutes (100 pairs) | **48.1** | **57.3** | **60.5%** |
| **WMT Biomedical & Healthcare** | Clinical Diagnoses & Dosages (100 pairs) | **48.7** | **60.3** | **50.3%** |

> **This measures general translation quality, not individual movies.** There's no professionally-translated Lao reference for these specific films to score against — that's the gap this project exists to fill. What you're seeing here is the underlying model's performance on standardized, independently-reviewable challenge sets (10 of each suite's 100 pairs are a deliberate stress-test variant of another pair in the same set, testing a known-hard discourse-marker pattern — not 100 fully independent sentences). For quality specific to the movies themselves, see **How We Verify Quality** above.

---


## 🎬 Case Studies: How the Model Learns

These are real, unedited before/after examples pulled directly from the verification corpus described above — not illustrative mockups. Each one shows the exact old published line, the exact new verified correction, and the reasoning the independent back-translation judge gave for approving the fix.

#### Screenplay Direction Fix — *Ad Astra*

- **Source (English):** "After a BEAT:"
- **❌ Legacy Output:** `ຫຼັງຈາກການຕີ:` <sub>(back-translates to: "One catch:")</sub>
- **✅ Verified Correction:** `ຈັກບຶດໜຶ່ງ,:`
- **Why:** The old translation took the screenwriting term "beat" (a pause) completely literally, producing the wrong meaning in Lao. The fix recognizes it as a stage direction, not a physical action. *Verification judge: "Both phrases function as a transitional cue indicating a pause or a significant point/condition is about to be addressed."*

#### Calque / Literal-Translation Fix — *10 Things I Hate About You*

- **Source (English):** "You're completely demented."
- **❌ Legacy Output:** `ເຈົ້າໂຊກຮ້າຍຢ່າງສົມບູນ.` <sub>(back-translates to: "You're really crazy.")</sub>
- **✅ Verified Correction:** `ເຈົ້າແມ່ນໂງ່ແທ້ໆ.`
- **Why:** A recurring, documented bug in this project: the model would sometimes translate "crazy/insane/demented" using the Lao word for "unlucky" (ໂຊກຮ້າຍ) instead of the correct word for "crazy" (ໂງ່) -- a literal-sounding but semantically wrong substitution. *Verification judge: "Both sentences express that the listener is mentally unstable, with 'demented' and 'crazy' functioning as near-synonyms in this context and the degree modifiers 'completely' and 'really' preserving the intensity."*

#### Calque / Literal-Translation Fix — *2001: A Space Odyssey*

- **Source (English):** "You're kidding."
- **❌ Legacy Output:** `ເຈົ້າໂຊກຮ້າຍ.` <sub>(back-translates to: "You're not serious.")</sub>
- **✅ Verified Correction:** `ເຈົ້າແມ່ນບໍ່ຈິງແລ້ວ.`
- **Why:** The same "unlucky"-for-"crazy" calque bug recurring independently in a different movie, confirming it was a systemic model bias rather than a one-off mistake in a single file. *Verification judge: "Both sentences function as rhetorical responses expressing disbelief or disbelief that the previous statement is true."*

#### Idiom / Slang Fix — *12 Monkeys*

- **Source (English):** "Push it tight!"
- **❌ Legacy Output:** `ກົດມັນຢ່າງເຂັ້ມງວດ!` <sub>(back-translates to: "Tighten up!")</sub>
- **✅ Verified Correction:** `ແໜ້ນໆເດີ້!`
- **Why:** The old line translated the English idiom word-for-word into a stiff, overly formal Lao command. The fix uses a natural spoken-Lao reduplication pattern a real speaker would actually say. *Verification judge: "Both sentences convey the imperative action of tightening something securely, with 'tighten up' being a standard idiomatic equivalent to 'push it tight'."*

#### Idiom / Slang Fix — *15 Minutes*

- **Source (English):** "In a minute, Ludwig."
- **❌ Legacy Output:** `ໃນນາທີຫນຶ່ງ, ລູດວິດຈ໌.` <sub>(back-translates to: "In a moment, Ludwig.")</sub>
- **✅ Verified Correction:** `ອີກບໍ່ດົນ, ລູດວິດິກ.`
- **Why:** "In a minute" was translated as a literal unit of time instead of the idiom "in a moment." The fix restores the natural, non-literal meaning. *Verification judge: "The phrases 'In a minute' and 'In a moment' are synonymous idioms for waiting a short time, and the entity 'Ludwig' is preserved in both."*

#### Hallucination Removal ("cat" substitution) — *The Lord of the Rings: The Fellowship of the Ring*

- **Source (English):** "So the ring of power has been found?"
- **❌ Legacy Output:** `ສະນັ້ນແມວຂອງພະລັງໄດ້ຖືກພົບເຫັນແລ້ວບໍ?` <sub>(back-translates to: "Yes, the power ring has been found?")</sub>
- **✅ Verified Correction:** `ແມ່ນແລ້ວແຫວນອໍານາດແມ່ນຖືກພົບແລ້ວບໍ່?`
- **Why:** A known model failure mode: the real, correctly-spelled Lao word for "cat" (ແມວ) sometimes appears as a filler substitution for completely unrelated words -- here standing in for "ring." The fix restores the actual entity from the English source. *Verification judge: "The sentences contain the same core entities (ring/power) and action (has been found), with only minor variations in article and word order that do not change the semantic meaning."*

#### Hallucination Removal (garbled fragment) — *Freddy vs. Jason*

- **Source (English):** "Hey! Watch that!"
- **❌ Legacy Output:** `ເຮ້! ເບິ່ງແມ!` <sub>(back-translates to: "Hello! Watch out!")</sub>
- **✅ Verified Correction:** `ສະບາຍດີ! ລະວັງເດີ້!`
- **Why:** The old translation ended in a bare, incomplete "ແມ" fragment -- a known decoder artifact that never finishes into a real word. The fix replaces it with an actual, complete Lao warning phrase. *Verification judge: "Both expressions function as greetings followed by urgent warnings to pay attention or avoid danger."*

---

## 🎬 Available Subtitles (287 Films · 238,841 Cues)

> 🔍 **Instant Live Search & Filters**:
> To instantly search by title, actor, year, or genre across all **287 movies**, visit our interactive web catalog:
> 🌐 👉 [**hieng1999.github.io/lao-subtitles**](https://hieng1999.github.io/lao-subtitles/)

### ⭐ Featured Spotlight (Top 10 Movies)
> chrF++/BLEU below are **round-trip fidelity** scores (published Lao translated back to English, compared to the original) — a real, computed number, but not a substitute for a human reference. See **How We Verify Quality** above for what that means.

| Movie Title | Year | Genre | Cues | chrF++ (round-trip) | BLEU (round-trip) | Subtitle Downloads | Verification Status |
|:---|:---:|:---|:---:|:---:|:---:|:---|:---|
| **10 Things I Hate About You** | **1999** | Romance | 1,027 | 62.0 | 45.7 | [🇱🇦 Lao](subtitles/10.Things.I.Hate.About.You.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/10.Things.I.Hate.About.You.1999.bilingual.srt) | ✓ 42 fixed |
| **Spider-Man: Across the Spider-Verse** | **2023** | Animation | 1,542 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Spider-Man.Across.the.Spider-Verse.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Spider-Man.Across.the.Spider-Verse.2023.bilingual.srt) | ✓ 57 fixed |
| **Toy Story** | **1995** | Animation | 887 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Toy.Story.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Toy.Story.1995.bilingual.srt) | ✓ 22 fixed |
| **Avengers: Endgame** | **2019** | Adventure | 1,144 | 63.4 | 50.6 | [🇱🇦 Lao](subtitles/Avengers.Endgame.2019.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Avengers.Endgame.2019.bilingual.srt) | ✓ 38 fixed |
| **Batman** | **1989** | Thriller | 609 | 59.6 | 45.5 | [🇱🇦 Lao](subtitles/Batman.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Batman.1989.bilingual.srt) | ✓ 16 fixed |
| **Wall-E** | **2008** | Animation | 476 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Wall-E.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Wall-E.2008.bilingual.srt) | ✓ 28 fixed |
| **American Beauty** | **1999** | Drama | 760 | 65.8 | 53.2 | [🇱🇦 Lao](subtitles/American.Beauty.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Beauty.1999.bilingual.srt) | ✓ 32 fixed |
| **Argo** | **2012** | Thriller | 759 | 58.3 | 38.9 | [🇱🇦 Lao](subtitles/Argo.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Argo.2012.bilingual.srt) | ✓ 19 fixed |
| **12** | **2007** | Comedy | 505 | 60.5 | 43.9 | [🇱🇦 Lao](subtitles/12.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.2007.bilingual.srt) | ✓ 30 fixed |
| **12 and Holding** | **2005** | Drama | 734 | 68.2 | 54.6 | [🇱🇦 Lao](subtitles/12.and.Holding.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.and.Holding.2005.bilingual.srt) | ✓ 21 fixed |

<details>
<summary><b>📜 Click here to expand &amp; browse all 287 movies (238,841 localized cues)...</b></summary>

<br/>

| Movie Title | Year | Genre | Cues | chrF++ (round-trip) | BLEU (round-trip) | Subtitle Downloads | Verification Status |
|:---|:---:|:---|:---:|:---:|:---:|:---|:---|
| **10 Things I Hate About You** | **1999** | Romance | 1,027 | 62.0 | 45.7 | [🇱🇦 Lao](subtitles/10.Things.I.Hate.About.You.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/10.Things.I.Hate.About.You.1999.bilingual.srt) | ✓ 42 fixed |
| **12** | **2007** | Comedy | 505 | 60.5 | 43.9 | [🇱🇦 Lao](subtitles/12.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.2007.bilingual.srt) | ✓ 30 fixed |
| **12 and Holding** | **2005** | Drama | 734 | 68.2 | 54.6 | [🇱🇦 Lao](subtitles/12.and.Holding.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.and.Holding.2005.bilingual.srt) | ✓ 21 fixed |
| **12 Monkeys** | **1995** | Thriller | 779 | 63.3 | 49.6 | [🇱🇦 Lao](subtitles/12.Monkeys.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.Monkeys.1995.bilingual.srt) | ✓ 23 fixed |
| **12 Years a Slave** | **2013** | Drama | 835 | 48.4 | 29.3 | [🇱🇦 Lao](subtitles/12.Years.a.Slave.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.Years.a.Slave.2013.bilingual.srt) | ✓ 21 fixed |
| **127 Hours** | **2010** | Thriller | 282 | 53.5 | 37.0 | [🇱🇦 Lao](subtitles/127.Hours.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/127.Hours.2010.bilingual.srt) | ✓ 3 fixed |
| **1492: Conquest of Paradise** | **1992** | Drama | 634 | 63.0 | 48.2 | [🇱🇦 Lao](subtitles/1492.Conquest.of.Paradise.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/1492.Conquest.of.Paradise.1992.bilingual.srt) | ✓ 17 fixed |
| **15 Minutes** | **2001** | Thriller | 1,015 | 63.8 | 49.2 | [🇱🇦 Lao](subtitles/15.Minutes.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/15.Minutes.2001.bilingual.srt) | ✓ 37 fixed |
| **17 Again** | **2009** | Romance | 817 | 65.8 | 53.3 | [🇱🇦 Lao](subtitles/17.Again.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/17.Again.2009.bilingual.srt) | ✓ 23 fixed |
| **2001: A Space Odyssey** | **1968** | Sci-Fi | 447 | 64.0 | 47.9 | [🇱🇦 Lao](subtitles/2001.A.Space.Odyssey.1968.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/2001.A.Space.Odyssey.1968.bilingual.srt) | ✓ 21 fixed |
| **2012** | **2009** | Thriller | 893 | 60.7 | 43.0 | [🇱🇦 Lao](subtitles/2012.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/2012.2009.bilingual.srt) | ✓ 40 fixed |
| **20th Century Women** | **2016** | Drama | 648 | 53.0 | 38.4 | [🇱🇦 Lao](subtitles/20th.Century.Women.2016.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/20th.Century.Women.2016.bilingual.srt) | ✓ 21 fixed |
| **28 Days Later** | **2002** | Sci-Fi | 609 | 60.9 | 47.2 | [🇱🇦 Lao](subtitles/28.Days.Later.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/28.Days.Later.2002.bilingual.srt) | ✓ 25 fixed |
| **30 Minutes or Less** | **2011** | Comedy | 961 | 62.0 | 48.5 | [🇱🇦 Lao](subtitles/30.Minutes.or.Less.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/30.Minutes.or.Less.2011.bilingual.srt) | ✓ 14 fixed |
| **42** | **2013** | Drama | 1,042 | 58.4 | 41.4 | [🇱🇦 Lao](subtitles/42.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/42.2013.bilingual.srt) | ✓ 30 fixed |
| **44 Inch Chest** | **2009** | Drama | 726 | 44.9 | 31.9 | [🇱🇦 Lao](subtitles/44.Inch.Chest.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/44.Inch.Chest.2009.bilingual.srt) | ✓ 28 fixed |
| **48 Hrs.** | **1982** | Thriller | 1,076 | 58.9 | 43.5 | [🇱🇦 Lao](subtitles/48.Hrs..1982.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/48.Hrs..1982.bilingual.srt) | ✓ 26 fixed |
| **50-50** | **2011** | Drama | 1,067 | 67.0 | 53.7 | [🇱🇦 Lao](subtitles/50-50.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/50-50.2011.bilingual.srt) | ✓ 48 fixed |
| **500 Days of Summer** | **2009** | Romance | 1,022 | 66.0 | 53.2 | [🇱🇦 Lao](subtitles/500.Days.of.Summer.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/500.Days.of.Summer.2009.bilingual.srt) | ✓ 73 fixed |
| **8MM** | **1999** | Thriller | 794 | 62.9 | 50.0 | [🇱🇦 Lao](subtitles/8MM.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/8MM.1999.bilingual.srt) | ✓ 18 fixed |
| **A Few Good Men** | **1992** | Thriller | 1,458 | 58.9 | 40.9 | [🇱🇦 Lao](subtitles/A.Few.Good.Men.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Few.Good.Men.1992.bilingual.srt) | ✓ 56 fixed |
| **A Good Person** | **2023** | Drama | 978 | 64.3 | 50.6 | [🇱🇦 Lao](subtitles/A.Good.Person.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Good.Person.2023.bilingual.srt) | ✓ 35 fixed |
| **A Million Miles Away** | **2023** | Drama | 706 | 65.2 | 50.0 | [🇱🇦 Lao](subtitles/A.Million.Miles.Away.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Million.Miles.Away.2023.bilingual.srt) | ✓ 30 fixed |
| **A Most Violent Year** | **2014** | Drama | 1,175 | 64.4 | 49.1 | [🇱🇦 Lao](subtitles/A.Most.Violent.Year.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Most.Violent.Year.2014.bilingual.srt) | ✓ 53 fixed |
| **A Prayer Before Dawn** | **2017** | Drama | 364 | 58.0 | 42.5 | [🇱🇦 Lao](subtitles/A.Prayer.Before.Dawn.2017.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Prayer.Before.Dawn.2017.bilingual.srt) | ✓ 10 fixed |
| **A Quiet Place** | **2018** | Sci-Fi | 90 | 65.8 | 52.0 | [🇱🇦 Lao](subtitles/A.Quiet.Place.2018.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Quiet.Place.2018.bilingual.srt) | ✓ 2 fixed |
| **A Real Pain** | **2024** | Drama | 871 | 63.2 | 47.1 | [🇱🇦 Lao](subtitles/A.Real.Pain.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Real.Pain.2024.bilingual.srt) | ✓ 36 fixed |
| **A Scanner Darkly** | **2006** | Drama | 1,117 | 59.6 | 43.2 | [🇱🇦 Lao](subtitles/A.Scanner.Darkly.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Scanner.Darkly.2006.bilingual.srt) | ✓ 34 fixed |
| **A Serious Man** | **2009** | Comedy | 825 | 46.9 | 29.1 | [🇱🇦 Lao](subtitles/A.Serious.Man.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Serious.Man.2009.bilingual.srt) | ✓ 21 fixed |
| **Above the Law** | **1988** | Action | 550 | 55.0 | 36.7 | [🇱🇦 Lao](subtitles/Above.the.Law.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Above.the.Law.1988.bilingual.srt) | ✓ 12 fixed |
| **Absolute Power** | **1997** | Thriller | 509 | 62.6 | 42.7 | [🇱🇦 Lao](subtitles/Absolute.Power.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Absolute.Power.1997.bilingual.srt) | ✓ 20 fixed |
| **Ad Astra** | **2019** | Thriller | 493 | 60.3 | 43.1 | [🇱🇦 Lao](subtitles/Ad.Astra.2019.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Ad.Astra.2019.bilingual.srt) | ✓ 18 fixed |
| **Adaptation** | **2002** | Drama | 820 | 61.4 | 45.5 | [🇱🇦 Lao](subtitles/Adaptation.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Adaptation.2002.bilingual.srt) | ✓ 17 fixed |
| **Affliction** | **1997** | Drama | 770 | 62.2 | 47.3 | [🇱🇦 Lao](subtitles/Affliction.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Affliction.1997.bilingual.srt) | ✓ 23 fixed |
| **After School Special** | **2003** | Comedy | 1,193 | 60.2 | 45.6 | [🇱🇦 Lao](subtitles/After.School.Special.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/After.School.Special.2003.bilingual.srt) | ✓ 38 fixed |
| **After.Life** | **2009** | Thriller | 809 | 59.3 | 43.4 | [🇱🇦 Lao](subtitles/After.Life.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/After.Life.2009.bilingual.srt) | ✓ 26 fixed |
| **Agnes of God** | **1985** | Drama | 944 | 64.6 | 51.6 | [🇱🇦 Lao](subtitles/Agnes.of.God.1985.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Agnes.of.God.1985.bilingual.srt) | ✓ 42 fixed |
| **Air** | **2023** | Drama | 834 | 58.9 | 41.9 | [🇱🇦 Lao](subtitles/Air.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Air.2023.bilingual.srt) | ✓ 57 fixed |
| **Air Force One** | **1997** | Thriller | 919 | 63.3 | 46.9 | [🇱🇦 Lao](subtitles/Air.Force.One.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Air.Force.One.1997.bilingual.srt) | ✓ 32 fixed |
| **Airplane** | **1980** | Romance | 627 | 64.3 | 50.1 | [🇱🇦 Lao](subtitles/Airplane.1980.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Airplane.1980.bilingual.srt) | ✓ 19 fixed |
| **Airplane 2: The Sequel** | **1982** | Sci-Fi | 937 | 58.3 | 40.4 | [🇱🇦 Lao](subtitles/Airplane.2.The.Sequel.1982.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Airplane.2.The.Sequel.1982.bilingual.srt) | ✓ 41 fixed |
| **Ali** | **2001** | Drama | 995 | 54.8 | 36.5 | [🇱🇦 Lao](subtitles/Ali.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Ali.2001.bilingual.srt) | ✓ 34 fixed |
| **Alien** | **1979** | Feature Film | 883 | 56.4 | 39.7 | [🇱🇦 Lao](subtitles/Alien.1979.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alien.1979.bilingual.srt) | ✓ 39 fixed |
| **Alien 3** | **1992** | Thriller | 689 | 62.4 | 45.4 | [🇱🇦 Lao](subtitles/Alien.3.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alien.3.1992.bilingual.srt) | ✓ 19 fixed |
| **Alien Nation** | **1988** | Sci-Fi | 544 | 61.6 | 45.9 | [🇱🇦 Lao](subtitles/Alien.Nation.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alien.Nation.1988.bilingual.srt) | ✓ 16 fixed |
| **Aliens** | **1986** | Thriller | 724 | 62.2 | 47.4 | [🇱🇦 Lao](subtitles/Aliens.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Aliens.1986.bilingual.srt) | ✓ 16 fixed |
| **All About Eve** | **1950** | Drama | 1,409 | 58.7 | 43.4 | [🇱🇦 Lao](subtitles/All.About.Eve.1950.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.About.Eve.1950.bilingual.srt) | ✓ 38 fixed |
| **All About Steve** | **2009** | Comedy | 777 | 59.8 | 42.0 | [🇱🇦 Lao](subtitles/All.About.Steve.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.About.Steve.2009.bilingual.srt) | ✓ 15 fixed |
| **All of Us Strangers** | **2023** | Romance | 621 | 63.7 | 49.7 | [🇱🇦 Lao](subtitles/All.of.Us.Strangers.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.of.Us.Strangers.2023.bilingual.srt) | ✓ 23 fixed |
| **All the King's Men** | **2006** | Drama | 1,078 | 63.8 | 50.7 | [🇱🇦 Lao](subtitles/All.the.Kings.Men.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.the.Kings.Men.2006.bilingual.srt) | ✓ 27 fixed |
| **All the President's Men** | **1976** | Thriller | 994 | 59.1 | 39.1 | [🇱🇦 Lao](subtitles/All.the.Presidents.Men.1976.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.the.Presidents.Men.1976.bilingual.srt) | ✓ 30 fixed |
| **Almost Famous** | **2000** | Romance | 1,037 | 64.6 | 50.0 | [🇱🇦 Lao](subtitles/Almost.Famous.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Almost.Famous.2000.bilingual.srt) | ✓ 27 fixed |
| **Alone in the Dark** | **2005** | Thriller | 402 | 66.0 | 52.2 | [🇱🇦 Lao](subtitles/Alone.in.the.Dark.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alone.in.the.Dark.2005.bilingual.srt) | ✓ 7 fixed |
| **Amadeus** | **1984** | Drama | 1,379 | 57.3 | 42.6 | [🇱🇦 Lao](subtitles/Amadeus.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Amadeus.1984.bilingual.srt) | ✓ 66 fixed |
| **Amelia** | **2009** | Drama | 882 | 57.6 | 41.0 | [🇱🇦 Lao](subtitles/Amelia.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Amelia.2009.bilingual.srt) | ✓ 11 fixed |
| **American Beauty** | **1999** | Drama | 760 | 65.8 | 53.2 | [🇱🇦 Lao](subtitles/American.Beauty.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Beauty.1999.bilingual.srt) | ✓ 32 fixed |
| **American Fiction** | **2023** | Drama | 1,025 | 63.5 | 49.2 | [🇱🇦 Lao](subtitles/American.Fiction.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Fiction.2023.bilingual.srt) | ✓ 28 fixed |
| **American Gangster** | **2007** | Drama | 839 | 67.0 | 51.8 | [🇱🇦 Lao](subtitles/American.Gangster.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Gangster.2007.bilingual.srt) | ✓ 30 fixed |
| **American Graffiti** | **1973** | Drama | 1,122 | 60.5 | 44.6 | [🇱🇦 Lao](subtitles/American.Graffiti.1973.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Graffiti.1973.bilingual.srt) | ✓ 37 fixed |
| **American History X** | **1998** | Thriller | 794 | 61.5 | 48.1 | [🇱🇦 Lao](subtitles/American.History.X.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.History.X.1998.bilingual.srt) | ✓ 21 fixed |
| **American Hustle** | **2013** | Drama | 1,225 | 64.0 | 48.2 | [🇱🇦 Lao](subtitles/American.Hustle.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Hustle.2013.bilingual.srt) | ✓ 31 fixed |
| **American Milkshake** | **2013** | Comedy | 801 | 63.0 | 47.3 | [🇱🇦 Lao](subtitles/American.Milkshake.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Milkshake.2013.bilingual.srt) | ✓ 34 fixed |
| **American Pie** | **1999** | Comedy | 927 | 62.1 | 48.5 | [🇱🇦 Lao](subtitles/American.Pie.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Pie.1999.bilingual.srt) | ✓ 30 fixed |
| **American Shaolin: King of Kickboxers II** | **1992** | Action | 599 | 55.9 | 40.7 | [🇱🇦 Lao](subtitles/American.Shaolin.King.of.Kickboxers.II.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Shaolin.King.of.Kickboxers.II.1992.bilingual.srt) | ✓ 18 fixed |
| **American Sniper** | **2014** | Action | 914 | 60.7 | 45.4 | [🇱🇦 Lao](subtitles/American.Sniper.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Sniper.2014.bilingual.srt) | ✓ 24 fixed |
| **American Splendor** | **2003** | Comedy | 584 | 62.8 | 45.6 | [🇱🇦 Lao](subtitles/American.Splendor.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Splendor.2003.bilingual.srt) | ✓ 14 fixed |
| **American Werewolf in London** | **1981** | Romance | 854 | 61.6 | 47.8 | [🇱🇦 Lao](subtitles/American.Werewolf.in.London.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Werewolf.in.London.1981.bilingual.srt) | ✓ 25 fixed |
| **Amour** | **2012** | Romance | 502 | 61.6 | 48.2 | [🇱🇦 Lao](subtitles/Amour.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Amour.2012.bilingual.srt) | ✓ 20 fixed |
| **Analyze That** | **2002** | Crime | 1,138 | 60.4 | 45.4 | [🇱🇦 Lao](subtitles/Analyze.That.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Analyze.That.2002.bilingual.srt) | ✓ 29 fixed |
| **Analyze This** | **1999** | Crime | 1,151 | 65.7 | 51.6 | [🇱🇦 Lao](subtitles/Analyze.This.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Analyze.This.1999.bilingual.srt) | ✓ 28 fixed |
| **Anastasia** | **1997** | Animation | 587 | 64.4 | 51.3 | [🇱🇦 Lao](subtitles/Anastasia.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Anastasia.1997.bilingual.srt) | ✓ 10 fixed |
| **Angel Eyes** | **2001** | Romance | 974 | 64.8 | 51.3 | [🇱🇦 Lao](subtitles/Angel.Eyes.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Angel.Eyes.2001.bilingual.srt) | ✓ 27 fixed |
| **Annie Hall** | **1977** | Romance | 1,291 | 61.0 | 46.4 | [🇱🇦 Lao](subtitles/Annie.Hall.1977.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Annie.Hall.1977.bilingual.srt) | ✓ 54 fixed |
| **Anonymous** | **2011** | Thriller | 820 | 57.1 | 41.2 | [🇱🇦 Lao](subtitles/Anonymous.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Anonymous.2011.bilingual.srt) | ✓ 23 fixed |
| **Anora** | **2024** | Romance | 1,137 | 62.9 | 50.2 | [🇱🇦 Lao](subtitles/Anora.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Anora.2024.bilingual.srt) | ✓ 39 fixed |
| **Antitrust** | **2001** | Thriller | 903 | 62.8 | 45.0 | [🇱🇦 Lao](subtitles/Antitrust.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Antitrust.2001.bilingual.srt) | ✓ 36 fixed |
| **Antz** | **1998** | Comedy | 438 | 60.5 | 49.1 | [🇱🇦 Lao](subtitles/Antz.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Antz.1998.bilingual.srt) | ✓ 17 fixed |
| **Apocalypse Now** | **1979** | Action | 968 | 57.1 | 36.6 | [🇱🇦 Lao](subtitles/Apocalypse.Now.1979.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Apocalypse.Now.1979.bilingual.srt) | ✓ 38 fixed |
| **April Fool's Day** | **1986** | Horror | 812 | 63.3 | 50.4 | [🇱🇦 Lao](subtitles/April.Fools.Day.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/April.Fools.Day.1986.bilingual.srt) | ✓ 36 fixed |
| **Apt Pupil** | **1998** | Thriller | 897 | 58.6 | 42.6 | [🇱🇦 Lao](subtitles/Apt.Pupil.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Apt.Pupil.1998.bilingual.srt) | ✓ 46 fixed |
| **Arbitrage** | **2012** | Thriller | 1,007 | 64.9 | 50.6 | [🇱🇦 Lao](subtitles/Arbitrage.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arbitrage.2012.bilingual.srt) | ✓ 26 fixed |
| **Arcade** | **1993** | Sci-Fi | 518 | 66.8 | 55.5 | [🇱🇦 Lao](subtitles/Arcade.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arcade.1993.bilingual.srt) | ✓ 14 fixed |
| **Arctic Blue** | **1993** | Thriller | 613 | 61.2 | 45.1 | [🇱🇦 Lao](subtitles/Arctic.Blue.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arctic.Blue.1993.bilingual.srt) | ✓ 12 fixed |
| **Argo** | **2012** | Thriller | 759 | 58.3 | 38.9 | [🇱🇦 Lao](subtitles/Argo.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Argo.2012.bilingual.srt) | ✓ 19 fixed |
| **Army of Darkness** | **1992** | Horror | 234 | 29.3 | 12.4 | [🇱🇦 Lao](subtitles/Army.of.Darkness.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Army.of.Darkness.1992.bilingual.srt) | ✓ Verified, no changes needed |
| **Arthur** | **2011** | Comedy | 1,003 | 60.8 | 45.6 | [🇱🇦 Lao](subtitles/Arthur.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arthur.2011.bilingual.srt) | ✓ 16 fixed |
| **As Good As It Gets** | **1997** | Romance | 824 | 60.4 | 46.8 | [🇱🇦 Lao](subtitles/As.Good.As.It.Gets.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/As.Good.As.It.Gets.1997.bilingual.srt) | ✓ 26 fixed |
| **Assassins** | **1995** | Thriller | 877 | 65.4 | 50.8 | [🇱🇦 Lao](subtitles/Assassins.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Assassins.1995.bilingual.srt) | ✓ 34 fixed |
| **Asteroid City** | **2023** | Sci-Fi | 820 | 61.1 | 43.6 | [🇱🇦 Lao](subtitles/Asteroid.City.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Asteroid.City.2023.bilingual.srt) | ✓ 35 fixed |
| **Austin Powers - International Man of Mystery** | **1997** | Comedy | 802 | 63.3 | 49.6 | [🇱🇦 Lao](subtitles/Austin.Powers.-.International.Man.of.Mystery.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Austin.Powers.-.International.Man.of.Mystery.1997.bilingual.srt) | ✓ 19 fixed |
| **Austin Powers - The Spy Who Shagged Me** | **1999** | Comedy | 773 | 60.8 | 47.3 | [🇱🇦 Lao](subtitles/Austin.Powers.-.The.Spy.Who.Shagged.Me.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Austin.Powers.-.The.Spy.Who.Shagged.Me.1999.bilingual.srt) | ✓ 15 fixed |
| **Authors Anonymous** | **2014** | Comedy | 765 | 67.2 | 52.4 | [🇱🇦 Lao](subtitles/Authors.Anonymous.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Authors.Anonymous.2014.bilingual.srt) | ✓ 21 fixed |
| **Autumn in New York** | **2000** | Romance | 916 | 64.3 | 50.5 | [🇱🇦 Lao](subtitles/Autumn.in.New.York.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Autumn.in.New.York.2000.bilingual.srt) | ✓ 45 fixed |
| **Avatar** | **2009** | Sci-Fi | 784 | 61.6 | 44.4 | [🇱🇦 Lao](subtitles/Avatar.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Avatar.2009.bilingual.srt) | ✓ 32 fixed |
| **Avengers: Endgame** | **2019** | Adventure | 1,144 | 63.4 | 50.6 | [🇱🇦 Lao](subtitles/Avengers.Endgame.2019.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Avengers.Endgame.2019.bilingual.srt) | ✓ 38 fixed |
| **Babel** | **2006** | Thriller | 1,031 | 66.9 | 54.7 | [🇱🇦 Lao](subtitles/Babel.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Babel.2006.bilingual.srt) | ✓ 27 fixed |
| **Bachelor Party** | **1984** | Comedy | 952 | 62.0 | 48.8 | [🇱🇦 Lao](subtitles/Bachelor.Party.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bachelor.Party.1984.bilingual.srt) | ✓ 23 fixed |
| **Backdraft** | **1991** | Thriller | 962 | 61.5 | 45.6 | [🇱🇦 Lao](subtitles/Backdraft.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Backdraft.1991.bilingual.srt) | ✓ 25 fixed |
| **Bad Boys** | **1995** | Comedy | 792 | 59.6 | 42.9 | [🇱🇦 Lao](subtitles/Bad.Boys.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Boys.1995.bilingual.srt) | ✓ 12 fixed |
| **Bad Country** | **2014** | Crime | 773 | 57.9 | 41.0 | [🇱🇦 Lao](subtitles/Bad.Country.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Country.2014.bilingual.srt) | ✓ 22 fixed |
| **Bad Day at Black Rock** | **1955** | Thriller | 781 | 59.6 | 44.0 | [🇱🇦 Lao](subtitles/Bad.Day.at.Black.Rock.1955.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Day.at.Black.Rock.1955.bilingual.srt) | ✓ 21 fixed |
| **Bad Dreams** | **1988** | Thriller | 732 | 63.7 | 50.8 | [🇱🇦 Lao](subtitles/Bad.Dreams.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Dreams.1988.bilingual.srt) | ✓ 28 fixed |
| **Bad Lieutenant** | **1992** | Crime | 332 | 54.1 | 38.2 | [🇱🇦 Lao](subtitles/Bad.Lieutenant.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Lieutenant.1992.bilingual.srt) | ✓ 6 fixed |
| **Bad Santa** | **2003** | Crime | 659 | 55.0 | 39.0 | [🇱🇦 Lao](subtitles/Bad.Santa.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Santa.2003.bilingual.srt) | ✓ 33 fixed |
| **Barbie** | **2023** | Adventure | 959 | 61.7 | 45.9 | [🇱🇦 Lao](subtitles/Barbie.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Barbie.2023.bilingual.srt) | ✓ 32 fixed |
| **Barry Lyndon** | **1975** | Romance | 787 | 54.5 | 36.0 | [🇱🇦 Lao](subtitles/Barry.Lyndon.1975.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Barry.Lyndon.1975.bilingual.srt) | ✓ 8 fixed |
| **Barton Fink** | **1991** | Thriller | 771 | 57.7 | 41.9 | [🇱🇦 Lao](subtitles/Barton.Fink.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Barton.Fink.1991.bilingual.srt) | ✓ 20 fixed |
| **Basic** | **2003** | Thriller | 1,059 | 55.6 | 38.9 | [🇱🇦 Lao](subtitles/Basic.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Basic.2003.bilingual.srt) | ✓ 19 fixed |
| **Basic Instinct** | **1992** | Thriller | 881 | 66.5 | 51.1 | [🇱🇦 Lao](subtitles/Basic.Instinct.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Basic.Instinct.1992.bilingual.srt) | ✓ 26 fixed |
| **Batman** | **1989** | Thriller | 609 | 59.6 | 45.5 | [🇱🇦 Lao](subtitles/Batman.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Batman.1989.bilingual.srt) | ✓ 16 fixed |
| **Batman 2** | **1992** | Thriller | 604 | 60.6 | 45.5 | [🇱🇦 Lao](subtitles/Batman.2.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Batman.2.1992.bilingual.srt) | ✓ 10 fixed |
| **Battle: Los Angeles** | **2011** | Sci-Fi | 681 | 50.4 | 34.2 | [🇱🇦 Lao](subtitles/Battle.Los.Angeles.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Battle.Los.Angeles.2011.bilingual.srt) | ✓ 4 fixed |
| **Beavis and Butt-head Do America** | **1996** | Animation | 703 | 58.5 | 43.8 | [🇱🇦 Lao](subtitles/Beavis.and.Butt-head.Do.America.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Beavis.and.Butt-head.Do.America.1996.bilingual.srt) | ✓ 15 fixed |
| **Beginners** | **2010** | Romance | 745 | 63.2 | 47.5 | [🇱🇦 Lao](subtitles/Beginners.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Beginners.2010.bilingual.srt) | ✓ 26 fixed |
| **Belle** | **2013** | Romance | 813 | 51.8 | 34.6 | [🇱🇦 Lao](subtitles/Belle.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Belle.2013.bilingual.srt) | ✓ 15 fixed |
| **Big Eyes** | **2014** | Crime | 835 | 55.8 | 40.2 | [🇱🇦 Lao](subtitles/Big.Eyes.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Big.Eyes.2014.bilingual.srt) | ✓ 16 fixed |
| **Big Fish** | **2003** | Adventure | 804 | 65.7 | 50.7 | [🇱🇦 Lao](subtitles/Big.Fish.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Big.Fish.2003.bilingual.srt) | ✓ 17 fixed |
| **Birdman** | **2014** | Romance | 1,099 | 62.0 | 49.0 | [🇱🇦 Lao](subtitles/Birdman.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Birdman.2014.bilingual.srt) | ✓ 36 fixed |
| **Birthday Girl** | **2001** | Romance | 593 | 62.3 | 48.2 | [🇱🇦 Lao](subtitles/Birthday.Girl.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Birthday.Girl.2001.bilingual.srt) | ✓ 23 fixed |
| **Black Panther** | **2018** | Sci-Fi | 923 | 55.7 | 36.5 | [🇱🇦 Lao](subtitles/Black.Panther.2018.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Black.Panther.2018.bilingual.srt) | ✓ 15 fixed |
| **Black Rain** | **1989** | Crime | 650 | 63.9 | 50.2 | [🇱🇦 Lao](subtitles/Black.Rain.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Black.Rain.1989.bilingual.srt) | ✓ 12 fixed |
| **BlacKkKlansman** | **2018** | Crime | 1,089 | 56.6 | 36.0 | [🇱🇦 Lao](subtitles/BlacKkKlansman.2018.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/BlacKkKlansman.2018.bilingual.srt) | ✓ 38 fixed |
| **Blade** | **1998** | Sci-Fi | 560 | 65.7 | 50.0 | [🇱🇦 Lao](subtitles/Blade.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.1998.bilingual.srt) | ✓ 18 fixed |
| **Blade II** | **2002** | Horror | 566 | 56.4 | 39.1 | [🇱🇦 Lao](subtitles/Blade.II.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.II.2002.bilingual.srt) | ✓ 8 fixed |
| **Blade Runner** | **1982** | Sci-Fi | 746 | 62.2 | 46.4 | [🇱🇦 Lao](subtitles/Blade.Runner.1982.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.Runner.1982.bilingual.srt) | ✓ 25 fixed |
| **Blade: Trinity** | **2004** | Horror | 574 | 57.9 | 40.4 | [🇱🇦 Lao](subtitles/Blade.Trinity.2004.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.Trinity.2004.bilingual.srt) | ✓ 13 fixed |
| **Blitz** | **2011** | Action | 602 | 62.6 | 49.1 | [🇱🇦 Lao](subtitles/Blitz.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blitz.2011.bilingual.srt) | ✓ 30 fixed |
| **Blood and Wine** | **1996** | Crime | 926 | 58.9 | 41.8 | [🇱🇦 Lao](subtitles/Blood.and.Wine.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blood.and.Wine.1996.bilingual.srt) | ✓ 23 fixed |
| **Blood Diamond** | **2006** | Feature Film | 1,443 | 59.7 | 41.5 | [🇱🇦 Lao](subtitles/Blood.Diamond.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blood.Diamond.2006.bilingual.srt) | ✓ 62 fixed |
| **Blow** | **2001** | Crime | 1,026 | 66.2 | 52.1 | [🇱🇦 Lao](subtitles/Blow.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blow.2001.bilingual.srt) | ✓ 34 fixed |
| **Blue Valentine** | **2010** | Romance | 679 | 64.7 | 52.5 | [🇱🇦 Lao](subtitles/Blue.Valentine.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blue.Valentine.2010.bilingual.srt) | ✓ 21 fixed |
| **Blue Velvet** | **1986** | Crime | 948 | 61.0 | 45.2 | [🇱🇦 Lao](subtitles/Blue.Velvet.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blue.Velvet.1986.bilingual.srt) | ✓ 31 fixed |
| **Body Heat** | **1981** | Crime | 871 | 65.0 | 51.0 | [🇱🇦 Lao](subtitles/Body.Heat.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Body.Heat.1981.bilingual.srt) | ✓ 20 fixed |
| **Body of Evidence** | **1993** | Romance | 928 | 64.0 | 47.3 | [🇱🇦 Lao](subtitles/Body.of.Evidence.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Body.of.Evidence.1993.bilingual.srt) | ✓ 27 fixed |
| **Bodyguard** | **1992** | Romance | 964 | 58.0 | 41.5 | [🇱🇦 Lao](subtitles/Bodyguard.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bodyguard.1992.bilingual.srt) | ✓ 21 fixed |
| **Bones** | **2001** | Horror | 696 | 61.1 | 45.1 | [🇱🇦 Lao](subtitles/Bones.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bones.2001.bilingual.srt) | ✓ 9 fixed |
| **Bonnie and Clyde** | **1967** | Romance | 736 | 59.8 | 43.8 | [🇱🇦 Lao](subtitles/Bonnie.and.Clyde.1967.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bonnie.and.Clyde.1967.bilingual.srt) | ✓ 28 fixed |
| **Bookworm** | **2024** | Adventure | 889 | 63.6 | 51.8 | [🇱🇦 Lao](subtitles/Bookworm.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bookworm.2024.bilingual.srt) | ✓ 20 fixed |
| **Boondock Saints 2: All Saints Day** | **2009** | Crime | 892 | 57.5 | 40.6 | [🇱🇦 Lao](subtitles/Boondock.Saints.2.All.Saints.Day.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Boondock.Saints.2.All.Saints.Day.2009.bilingual.srt) | ✓ 24 fixed |
| **Bottle Rocket** | **1996** | Crime | 1,195 | 64.9 | 51.2 | [🇱🇦 Lao](subtitles/Bottle.Rocket.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bottle.Rocket.1996.bilingual.srt) | ✓ 57 fixed |
| **Bound** | **1996** | Crime | 918 | 68.3 | 55.7 | [🇱🇦 Lao](subtitles/Bound.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bound.1996.bilingual.srt) | ✓ 31 fixed |
| **Brazil** | **1985** | Sci-Fi | 912 | 59.2 | 46.3 | [🇱🇦 Lao](subtitles/Brazil.1985.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Brazil.1985.bilingual.srt) | ✓ 26 fixed |
| **Broadcast News** | **1987** | Romance | 1,127 | 63.5 | 47.4 | [🇱🇦 Lao](subtitles/Broadcast.News.1987.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Broadcast.News.1987.bilingual.srt) | ✓ 58 fixed |
| **Broken Arrow** | **1996** | Adventure | 921 | 57.8 | 39.8 | [🇱🇦 Lao](subtitles/Broken.Arrow.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Broken.Arrow.1996.bilingual.srt) | ✓ 14 fixed |
| **Broken Embraces** | **2009** | Romance | 991 | 61.6 | 47.7 | [🇱🇦 Lao](subtitles/Broken.Embraces.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Broken.Embraces.2009.bilingual.srt) | ✓ 22 fixed |
| **Bruce Almighty** | **2003** | Romance | 837 | 54.2 | 38.8 | [🇱🇦 Lao](subtitles/Bruce.Almighty.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bruce.Almighty.2003.bilingual.srt) | ✓ 11 fixed |
| **Buffy the Vampire Slayer** | **1992** | Horror | 941 | 62.9 | 48.5 | [🇱🇦 Lao](subtitles/Buffy.the.Vampire.Slayer.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Buffy.the.Vampire.Slayer.1992.bilingual.srt) | ✓ 33 fixed |
| **Bull Durham** | **1988** | Romance | 884 | 58.6 | 40.4 | [🇱🇦 Lao](subtitles/Bull.Durham.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bull.Durham.1988.bilingual.srt) | ✓ 13 fixed |
| **Burlesque** | **2010** | Romance | 1,041 | 55.5 | 39.7 | [🇱🇦 Lao](subtitles/Burlesque.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Burlesque.2010.bilingual.srt) | ✓ 28 fixed |
| **Burn After Reading** | **2008** | Crime | 1,052 | 60.5 | 46.1 | [🇱🇦 Lao](subtitles/Burn.After.Reading.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Burn.After.Reading.2008.bilingual.srt) | ✓ 45 fixed |
| **Burning Annie** | **2004** | Romance | 1,165 | 67.2 | 54.2 | [🇱🇦 Lao](subtitles/Burning.Annie.2004.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Burning.Annie.2004.bilingual.srt) | ✓ 35 fixed |
| **Capote** | **2005** | Crime | 768 | 63.0 | 47.5 | [🇱🇦 Lao](subtitles/Capote.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Capote.2005.bilingual.srt) | ✓ 31 fixed |
| **Carrie** | **1976** | Horror | 719 | 61.3 | 49.1 | [🇱🇦 Lao](subtitles/Carrie.1976.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Carrie.1976.bilingual.srt) | ✓ 38 fixed |
| **Cars 2** | **2011** | Animation | 1,226 | 61.8 | 47.4 | [🇱🇦 Lao](subtitles/Cars.2.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cars.2.2011.bilingual.srt) | ✓ 39 fixed |
| **Case 39** | **2009** | Horror | 746 | 66.0 | 52.6 | [🇱🇦 Lao](subtitles/Case.39.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Case.39.2009.bilingual.srt) | ✓ 28 fixed |
| **Casino** | **1995** | Crime | 2,483 | 61.1 | 46.6 | [🇱🇦 Lao](subtitles/Casino.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Casino.1995.bilingual.srt) | ✓ 110 fixed |
| **Cast Away** | **2000** | Adventure | 787 | 62.1 | 46.4 | [🇱🇦 Lao](subtitles/Cast.Away.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cast.Away.2000.bilingual.srt) | ✓ 35 fixed |
| **Catch Me If You Can** | **2002** | Crime | 933 | 62.5 | 45.1 | [🇱🇦 Lao](subtitles/Catch.Me.If.You.Can.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Catch.Me.If.You.Can.2002.bilingual.srt) | ✓ 13 fixed |
| **Charade** | **1963** | Romance | 1,355 | 59.7 | 40.7 | [🇱🇦 Lao](subtitles/Charade.1963.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Charade.1963.bilingual.srt) | ✓ 31 fixed |
| **Chasing Amy** | **1997** | Romance | 1,075 | 56.5 | 40.3 | [🇱🇦 Lao](subtitles/Chasing.Amy.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Chasing.Amy.1997.bilingual.srt) | ✓ 28 fixed |
| **Cherry Falls** | **2000** | Horror | 701 | 65.3 | 50.0 | [🇱🇦 Lao](subtitles/Cherry.Falls.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cherry.Falls.2000.bilingual.srt) | ✓ 33 fixed |
| **Chronicle** | **2012** | Sci-Fi | 738 | 59.9 | 43.9 | [🇱🇦 Lao](subtitles/Chronicle.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Chronicle.2012.bilingual.srt) | ✓ 18 fixed |
| **Chronicles of Narnia: The Lion, the Witch and the Wardrobe** | **2005** | Adventure | 629 | 60.1 | 45.3 | [🇱🇦 Lao](subtitles/Chronicles.of.Narnia.The.Lion.the.Witch.and.the.Wardrobe.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Chronicles.of.Narnia.The.Lion.the.Witch.and.the.Wardrobe.2005.bilingual.srt) | ✓ 9 fixed |
| **Cinema Paradiso** | **1988** | Romance | 457 | 64.3 | 51.5 | [🇱🇦 Lao](subtitles/Cinema.Paradiso.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cinema.Paradiso.1988.bilingual.srt) | ✓ 12 fixed |
| **Cirque du Freak: The Vampire's Assistant** | **2009** | Adventure | 938 | 51.4 | 34.6 | [🇱🇦 Lao](subtitles/Cirque.du.Freak.The.Vampires.Assistant.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cirque.du.Freak.The.Vampires.Assistant.2009.bilingual.srt) | ✓ 12 fixed |
| **Clash of the Titans** | **2010** | Adventure | 764 | 52.5 | 34.7 | [🇱🇦 Lao](subtitles/Clash.of.the.Titans.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Clash.of.the.Titans.2010.bilingual.srt) | ✓ 11 fixed |
| **Cliffhanger** | **1993** | Adventure | 559 | 60.0 | 41.2 | [🇱🇦 Lao](subtitles/Cliffhanger.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cliffhanger.1993.bilingual.srt) | ✓ 12 fixed |
| **Coco** | **2017** | Feature Film | 1,444 | 60.7 | 48.0 | [🇱🇦 Lao](subtitles/Coco.2017.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Coco.2017.bilingual.srt) | ✓ 50 fixed |
| **Constantine** | **2005** | Horror | 721 | 53.3 | 34.9 | [🇱🇦 Lao](subtitles/Constantine.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Constantine.2005.bilingual.srt) | ✓ 15 fixed |
| **Copycat** | **1995** | Horror | 843 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Copycat.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Copycat.1995.bilingual.srt) | ✓ 18 fixed |
| **Coraline** | **2009** | Animation | 804 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Coraline.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Coraline.2009.bilingual.srt) | ✓ 25 fixed |
| **Corpse Bride** | **2005** | Animation | 495 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Corpse.Bride.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Corpse.Bride.2005.bilingual.srt) | ✓ 11 fixed |
| **Crouching Tiger, Hidden Dragon** | **2000** | Adventure | 531 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Crouching.Tiger.Hidden.Dragon.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Crouching.Tiger.Hidden.Dragon.2000.bilingual.srt) | ✓ 17 fixed |
| **Dances with Wolves** | **1990** | Adventure | 638 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Dances.with.Wolves.1990.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dances.with.Wolves.1990.bilingual.srt) | ✓ 13 fixed |
| **Dark City** | **1998** | Sci-Fi | 560 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Dark.City.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dark.City.1998.bilingual.srt) | ✓ 12 fixed |
| **Dark Star** | **1974** | Sci-Fi | 350 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Dark.Star.1974.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dark.Star.1974.bilingual.srt) | ✓ 15 fixed |
| **Darkman** | **1990** | Sci-Fi | 930 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Darkman.1990.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Darkman.1990.bilingual.srt) | ✓ 9 fixed |
| **Dawn of the Dead** | **2004** | Horror | 139 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Dawn.of.the.Dead.2004.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dawn.of.the.Dead.2004.bilingual.srt) | ✓ 2 fixed |
| **Deadpool** | **2016** | Adventure | 742 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Deadpool.2016.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Deadpool.2016.bilingual.srt) | ✓ 23 fixed |
| **Deadpool & Wolverine** | **2024** | Sci-Fi | 742 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Deadpool.and.Wolverine.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Deadpool.and.Wolverine.2024.bilingual.srt) | ✓ 22 fixed |
| **Deep Rising** | **1998** | Horror | 632 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Deep.Rising.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Deep.Rising.1998.bilingual.srt) | ✓ 22 fixed |
| **Despicable Me 2** | **2013** | Animation | 710 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Despicable.Me.2.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Despicable.Me.2.2013.bilingual.srt) | ✓ 27 fixed |
| **Detroit Rock City** | **1999** | Adventure | 777 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Detroit.Rock.City.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Detroit.Rock.City.1999.bilingual.srt) | ✓ 8 fixed |
| **Devil's Advocate** | **1997** | Horror | 1,060 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Devils.Advocate.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Devils.Advocate.1997.bilingual.srt) | ✓ 37 fixed |
| **Django Unchained** | **2012** | Adventure | 1,067 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Django.Unchained.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Django.Unchained.2012.bilingual.srt) | ✓ 20 fixed |
| **Dogma** | **1999** | Adventure | 955 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Dogma.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dogma.1999.bilingual.srt) | ✓ 18 fixed |
| **Drag Me to Hell** | **2009** | Horror | 665 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Drag.Me.to.Hell.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Drag.Me.to.Hell.2009.bilingual.srt) | ✓ 20 fixed |
| **Dune** | **1984** | Sci-Fi | 617 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Dune.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dune.1984.bilingual.srt) | ✓ 13 fixed |
| **Dune Part One** | **2021** | Sci-Fi | 648 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Dune.Part.One.2021.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dune.Part.One.2021.bilingual.srt) | ✓ 20 fixed |
| **Eight Legged Freaks** | **2002** | Sci-Fi | 675 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Eight.Legged.Freaks.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Eight.Legged.Freaks.2002.bilingual.srt) | ✓ 17 fixed |
| **Elemental** | **2023** | Animation | 906 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Elemental.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Elemental.2023.bilingual.srt) | ✓ 36 fixed |
| **Escape From L.A.** | **1996** | Sci-Fi | 617 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Escape.From.L.A..1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Escape.From.L.A..1996.bilingual.srt) | ✓ 12 fixed |
| **Event Horizon** | **1997** | Horror | 892 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Event.Horizon.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Event.Horizon.1997.bilingual.srt) | ✓ 42 fixed |
| **Evil Dead** | **1981** | Horror | 310 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Evil.Dead.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Evil.Dead.1981.bilingual.srt) | ✓ 18 fixed |
| **Evil Dead II: Dead by Dawn** | **1987** | Horror | 221 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Evil.Dead.II.Dead.by.Dawn.1987.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Evil.Dead.II.Dead.by.Dawn.1987.bilingual.srt) | ✓ 4 fixed |
| **Fantastic Mr Fox** | **2009** | Animation | 625 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Fantastic.Mr.Fox.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Fantastic.Mr.Fox.2009.bilingual.srt) | ✓ 12 fixed |
| **Feast** | **2005** | Horror | 831 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Feast.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Feast.2005.bilingual.srt) | ✓ 34 fixed |
| **Fight Club** | **1999** | Drama / Classics | 1,293 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Fight.Club.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Fight.Club.1999.bilingual.srt) | ✓ 34 fixed |
| **Final Destination** | **2000** | Horror | 447 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Final.Destination.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Final.Destination.2000.bilingual.srt) | ✓ 13 fixed |
| **Final Destination 2** | **2003** | Horror | 648 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Final.Destination.2.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Final.Destination.2.2003.bilingual.srt) | ✓ 14 fixed |
| **Forrest Gump** | **1994** | Drama / Classics | 1,065 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Forrest.Gump.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Forrest.Gump.1994.bilingual.srt) | ✓ 32 fixed |
| **Freddy vs. Jason** | **2003** | Horror | 716 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Freddy.vs..Jason.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Freddy.vs..Jason.2003.bilingual.srt) | ✓ 25 fixed |
| **Friday the 13th** | **1980** | Horror | 432 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Friday.the.13th.1980.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Friday.the.13th.1980.bilingual.srt) | ✓ 25 fixed |
| **Friday the 13th Part VIII: Jason Takes Manhattan** | **1989** | Horror | 569 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Friday.the.13th.Part.VIII.Jason.Takes.Manhattan.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Friday.the.13th.Part.VIII.Jason.Takes.Manhattan.1989.bilingual.srt) | ✓ 17 fixed |
| **Fright Night** | **1985** | Horror | 883 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Fright.Night.1985.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Fright.Night.1985.bilingual.srt) | ✓ 13 fixed |
| **Frozen** | **2013** | Feature Film | 1,652 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Frozen.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Frozen.2013.bilingual.srt) | ✓ 75 fixed |
| **Frozen** | **2013** | Animation | 917 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Frozen.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Frozen.2013.bilingual.srt) | ✓ 23 fixed |
| **Gladiator** | **2000** | Drama / Classics | 675 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Gladiator.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Gladiator.2000.bilingual.srt) | ✓ 18 fixed |
| **Happy Feet** | **2006** | Animation | 633 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Happy.Feet.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Happy.Feet.2006.bilingual.srt) | ✓ 10 fixed |
| **Heavy Metal** | **1981** | Animation | 297 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Heavy.Metal.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Heavy.Metal.1981.bilingual.srt) | ✓ 8 fixed |
| **Here Comes Peter Cottontail** | **1971** | Animation | 508 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Here.Comes.Peter.Cottontail.1971.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Here.Comes.Peter.Cottontail.1971.bilingual.srt) | ✓ 9 fixed |
| **How to Train Your Dragon** | **2010** | Animation | 785 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/How.to.Train.Your.Dragon.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/How.to.Train.Your.Dragon.2010.bilingual.srt) | ✓ 19 fixed |
| **How to Train Your Dragon 2** | **2014** | Animation | 726 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/How.to.Train.Your.Dragon.2.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/How.to.Train.Your.Dragon.2.2014.bilingual.srt) | ✓ 13 fixed |
| **Inception** | **2010** | Drama / Classics | 1,223 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Inception.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Inception.2010.bilingual.srt) | ✓ 33 fixed |
| **Interstellar** | **2014** | Drama / Classics | 902 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Interstellar.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Interstellar.2014.bilingual.srt) | ✓ 10 fixed |
| **Kung Fu Panda** | **2008** | Animation | 694 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Kung.Fu.Panda.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Kung.Fu.Panda.2008.bilingual.srt) | ✓ 26 fixed |
| **L' Avventura (The Adventure)** | **1960** | Thriller | 745 | 63.0 | 49.9 | [🇱🇦 Lao](subtitles/L.Avventura.The.Adventure.1960.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/L.Avventura.The.Adventure.1960.bilingual.srt) | ✓ 18 fixed |
| **Megamind** | **2010** | Animation | 866 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Megamind.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Megamind.2010.bilingual.srt) | ✓ 31 fixed |
| **Memento** | **2000** | Feature Film | 692 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Memento.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Memento.2000.bilingual.srt) | ✓ 25 fixed |
| **Moana** | **2016** | Feature Film | 1,233 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Moana.2016.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Moana.2016.bilingual.srt) | ✓ 67 fixed |
| **Monkeybone** | **2001** | Animation | 643 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Monkeybone.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Monkeybone.2001.bilingual.srt) | ✓ 13 fixed |
| **One Eight Seven (187)** | **1997** | Drama | 754 | 61.3 | 44.5 | [🇱🇦 Lao](subtitles/One.Eight.Seven.187.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/One.Eight.Seven.187.1997.bilingual.srt) | ✓ 20 fixed |
| **Onward** | **2020** | Animation | 1,114 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Onward.2020.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Onward.2020.bilingual.srt) | ✓ 27 fixed |
| **ParaNorman** | **2012** | Animation | 664 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/ParaNorman.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/ParaNorman.2012.bilingual.srt) | ✓ 19 fixed |
| **Pulp Fiction** | **1994** | Drama / Classics | 1,214 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Pulp.Fiction.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Pulp.Fiction.1994.bilingual.srt) | ✓ 44 fixed |
| **Puss in Boots: The Last Wish** | **2022** | Animation | 1,134 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Puss.in.Boots.The.Last.Wish.2022.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Puss.in.Boots.The.Last.Wish.2022.bilingual.srt) | ✓ 36 fixed |
| **Reservoir Dogs** | **1992** | Feature Film | 694 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Reservoir.Dogs.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Reservoir.Dogs.1992.bilingual.srt) | ✓ 14 fixed |
| **Rise of the Guardians** | **2012** | Animation | 984 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Rise.of.the.Guardians.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Rise.of.the.Guardians.2012.bilingual.srt) | ✓ 24 fixed |
| **Saving Private Ryan** | **1998** | Feature Film | 934 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Saving.Private.Ryan.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Saving.Private.Ryan.1998.bilingual.srt) | ✓ 23 fixed |
| **Se7en** | **1995** | Feature Film | 489 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Se7en.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Se7en.1995.bilingual.srt) | ✓ 6 fixed |
| **Shrek** | **2001** | Animation | 744 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Shrek.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Shrek.2001.bilingual.srt) | ✓ 19 fixed |
| **Shrek the Third** | **2007** | Animation | 894 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Shrek.the.Third.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Shrek.the.Third.2007.bilingual.srt) | ✓ 49 fixed |
| **South Park: Bigger, Longer & Uncut** | **1999** | Animation | 1,257 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/South.Park.Bigger.Longer.and.Uncut.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/South.Park.Bigger.Longer.and.Uncut.1999.bilingual.srt) | ✓ 36 fixed |
| **Spider-Man: Across the Spider-Verse** | **2023** | Animation | 1,542 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Spider-Man.Across.the.Spider-Verse.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Spider-Man.Across.the.Spider-Verse.2023.bilingual.srt) | ✓ 57 fixed |
| **Star Wars: Episode IV - A New Hope** | **1977** | Feature Film | 994 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Star.Wars.Episode.IV.-.A.New.Hope.1977.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Star.Wars.Episode.IV.-.A.New.Hope.1977.bilingual.srt) | ✓ 18 fixed |
| **Teenage Mutant Ninja Turtles: Mutant Mayhem** | **2023** | Animation | 996 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Teenage.Mutant.Ninja.Turtles.Mutant.Mayhem.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Teenage.Mutant.Ninja.Turtles.Mutant.Mayhem.2023.bilingual.srt) | ✓ 37 fixed |
| **Terminator 2: Judgment Day** | **1991** | Feature Film | 518 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Terminator.2.Judgment.Day.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Terminator.2.Judgment.Day.1991.bilingual.srt) | ✓ 15 fixed |
| **The Abyss** | **1989** | Thriller | 665 | 60.0 | 45.6 | [🇱🇦 Lao](subtitles/The.Abyss.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Abyss.1989.bilingual.srt) | ✓ 22 fixed |
| **The Addams Family** | **1991** | Horror | 265 | 54.3 | 38.6 | [🇱🇦 Lao](subtitles/The.Addams.Family.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Addams.Family.1991.bilingual.srt) | ✓ 5 fixed |
| **The Adjustment Bureau** | **2011** | Thriller | 978 | 61.2 | 44.2 | [🇱🇦 Lao](subtitles/The.Adjustment.Bureau.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Adjustment.Bureau.2011.bilingual.srt) | ✓ 14 fixed |
| **The American** | **2010** | Thriller | 693 | 61.3 | 46.8 | [🇱🇦 Lao](subtitles/The.American.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.American.2010.bilingual.srt) | ✓ 34 fixed |
| **The American President** | **1995** | Romance | 1,403 | 64.3 | 48.7 | [🇱🇦 Lao](subtitles/The.American.President.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.American.President.1995.bilingual.srt) | ✓ 37 fixed |
| **The Amityville Asylum** | **2013** | Horror | 631 | 59.3 | 43.5 | [🇱🇦 Lao](subtitles/The.Amityville.Asylum.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Amityville.Asylum.2013.bilingual.srt) | ✓ 17 fixed |
| **The Apartment** | **1960** | Comedy | 1,214 | 64.0 | 45.1 | [🇱🇦 Lao](subtitles/The.Apartment.1960.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Apartment.1960.bilingual.srt) | ✓ 43 fixed |
| **The Assignment** | **1997** | Thriller | 788 | 61.3 | 46.9 | [🇱🇦 Lao](subtitles/The.Assignment.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Assignment.1997.bilingual.srt) | ✓ 19 fixed |
| **The Avengers** | **2012** | Sci-Fi | 941 | 54.6 | 38.2 | [🇱🇦 Lao](subtitles/The.Avengers.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Avengers.2012.bilingual.srt) | ✓ 20 fixed |
| **The Back-up Plan** | **2010** | Romance | 1,058 | 60.0 | 44.8 | [🇱🇦 Lao](subtitles/The.Back-up.Plan.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Back-up.Plan.2010.bilingual.srt) | ✓ 71 fixed |
| **The Battle of Shaker Heights** | **2003** | Romance | 945 | 63.8 | 49.2 | [🇱🇦 Lao](subtitles/The.Battle.of.Shaker.Heights.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Battle.of.Shaker.Heights.2003.bilingual.srt) | ✓ 33 fixed |
| **The Beekeeper** | **2024** | Thriller | 762 | 61.8 | 45.9 | [🇱🇦 Lao](subtitles/The.Beekeeper.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Beekeeper.2024.bilingual.srt) | ✓ 19 fixed |
| **The Big Blue** | **1988** | Romance | 849 | 64.4 | 50.5 | [🇱🇦 Lao](subtitles/The.Big.Blue.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Big.Blue.1988.bilingual.srt) | ✓ 27 fixed |
| **The Big Sick** | **2017** | Romance | 1,119 | 65.0 | 49.7 | [🇱🇦 Lao](subtitles/The.Big.Sick.2017.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Big.Sick.2017.bilingual.srt) | ✓ 42 fixed |
| **The Big White** | **2005** | Crime | 840 | 64.1 | 50.4 | [🇱🇦 Lao](subtitles/The.Big.White.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Big.White.2005.bilingual.srt) | ✓ 34 fixed |
| **The Birds** | **1963** | Romance | 1,139 | 61.6 | 48.0 | [🇱🇦 Lao](subtitles/The.Birds.1963.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Birds.1963.bilingual.srt) | ✓ 34 fixed |
| **The Black Dahlia** | **2006** | Crime | 1,048 | 59.9 | 43.0 | [🇱🇦 Lao](subtitles/The.Black.Dahlia.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Black.Dahlia.2006.bilingual.srt) | ✓ 32 fixed |
| **The Blast from the Past** | **1999** | Romance | 1,268 | 63.0 | 50.5 | [🇱🇦 Lao](subtitles/The.Blast.from.the.Past.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Blast.from.the.Past.1999.bilingual.srt) | ✓ 52 fixed |
| **The Bling Ring** | **2013** | Crime | 606 | 64.9 | 49.1 | [🇱🇦 Lao](subtitles/The.Bling.Ring.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bling.Ring.2013.bilingual.srt) | ✓ 25 fixed |
| **The Book of Eli** | **2010** | Sci-Fi | 786 | 64.5 | 50.6 | [🇱🇦 Lao](subtitles/The.Book.of.Eli.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Book.of.Eli.2010.bilingual.srt) | ✓ 28 fixed |
| **The Boondock Saints** | **1999** | Crime | 787 | 57.3 | 40.9 | [🇱🇦 Lao](subtitles/The.Boondock.Saints.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Boondock.Saints.1999.bilingual.srt) | ✓ 14 fixed |
| **The Bounty Hunter** | **2010** | Romance | 934 | 64.9 | 53.0 | [🇱🇦 Lao](subtitles/The.Bounty.Hunter.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bounty.Hunter.2010.bilingual.srt) | ✓ 28 fixed |
| **The Bourne Identity** | **2002** | Adventure | 643 | 61.3 | 43.0 | [🇱🇦 Lao](subtitles/The.Bourne.Identity.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bourne.Identity.2002.bilingual.srt) | ✓ 22 fixed |
| **The Bourne Ultimatum** | **2007** | Adventure | 553 | 66.8 | 52.2 | [🇱🇦 Lao](subtitles/The.Bourne.Ultimatum.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bourne.Ultimatum.2007.bilingual.srt) | ✓ 26 fixed |
| **The Box** | **2009** | Sci-Fi | 811 | 61.5 | 47.9 | [🇱🇦 Lao](subtitles/The.Box.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Box.2009.bilingual.srt) | ✓ 15 fixed |
| **The Boxtrolls** | **2014** | Animation | 938 | 54.6 | 40.5 | [🇱🇦 Lao](subtitles/The.Boxtrolls.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Boxtrolls.2014.bilingual.srt) | ✓ 27 fixed |
| **The Brothers Bloom** | **2008** | Romance | 706 | 61.7 | 45.7 | [🇱🇦 Lao](subtitles/The.Brothers.Bloom.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Brothers.Bloom.2008.bilingual.srt) | ✓ 18 fixed |
| **The Cell** | **2000** | Sci-Fi | 621 | 65.5 | 51.3 | [🇱🇦 Lao](subtitles/The.Cell.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Cell.2000.bilingual.srt) | ✓ 20 fixed |
| **The Cider House Rules** | **1999** | Romance | 1,020 | 62.6 | 45.9 | [🇱🇦 Lao](subtitles/The.Cider.House.Rules.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Cider.House.Rules.1999.bilingual.srt) | ✓ 31 fixed |
| **The Croods** | **2013** | Animation | 805 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Croods.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Croods.2013.bilingual.srt) | ✓ 22 fixed |
| **The Crow** | **1994** | Horror | 539 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Crow.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Crow.1994.bilingual.srt) | ✓ 12 fixed |
| **The Crow Salvation** | **2000** | Horror | 572 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Crow.Salvation.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Crow.Salvation.2000.bilingual.srt) | ✓ 12 fixed |
| **The Dark Knight** | **2008** | Drama / Classics | 1,243 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Dark.Knight.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Dark.Knight.2008.bilingual.srt) | ✓ 24 fixed |
| **The Day the Earth Stood Still** | **2008** | Sci-Fi | 770 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Day.the.Earth.Stood.Still.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Day.the.Earth.Stood.Still.2008.bilingual.srt) | ✓ 19 fixed |
| **The Departed** | **2006** | Feature Film | 1,180 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Departed.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Departed.2006.bilingual.srt) | ✓ 36 fixed |
| **The Godfather** | **1972** | Drama / Classics | 899 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Godfather.1972.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Godfather.1972.bilingual.srt) | ✓ 23 fixed |
| **The Green Mile** | **1999** | Feature Film | 1,012 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Green.Mile.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Green.Mile.1999.bilingual.srt) | ✓ 23 fixed |
| **The LEGO Movie** | **2014** | Animation | 961 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.LEGO.Movie.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.LEGO.Movie.2014.bilingual.srt) | ✓ 38 fixed |
| **The Lord of the Rings: The Fellowship of the Ring** | **2001** | Feature Film | 817 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Lord.of.the.Rings.The.Fellowship.of.the.Ring.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Lord.of.the.Rings.The.Fellowship.of.the.Ring.2001.bilingual.srt) | ✓ 21 fixed |
| **The Matrix** | **1999** | Drama / Classics | 568 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Matrix.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Matrix.1999.bilingual.srt) | ✓ 12 fixed |
| **The Prestige** | **2006** | Feature Film | 1,047 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Prestige.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Prestige.2006.bilingual.srt) | ✓ 17 fixed |
| **The Shawshank Redemption** | **1994** | Feature Film | 803 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Shawshank.Redemption.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Shawshank.Redemption.1994.bilingual.srt) | ✓ 22 fixed |
| **The Silence Of The Lambs** | **1991** | Feature Film | 928 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Silence.Of.The.Lambs.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Silence.Of.The.Lambs.1991.bilingual.srt) | ✓ 8 fixed |
| **The Terminator** | **1984** | Feature Film | 503 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Terminator.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Terminator.1984.bilingual.srt) | ✓ 24 fixed |
| **The Usual Suspects** | **1995** | Feature Film | 768 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/The.Usual.Suspects.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Usual.Suspects.1995.bilingual.srt) | ✓ 24 fixed |
| **TMNT** | **2007** | Animation | 551 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/TMNT.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/TMNT.2007.bilingual.srt) | ✓ 9 fixed |
| **Toy Story** | **1995** | Animation | 887 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Toy.Story.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Toy.Story.1995.bilingual.srt) | ✓ 22 fixed |
| **Transformers: The Movie** | **1986** | Animation | 720 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Transformers.The.Movie.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Transformers.The.Movie.1986.bilingual.srt) | ✓ 15 fixed |
| **Up** | **2009** | Animation | 720 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Up.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Up.2009.bilingual.srt) | ✓ 17 fixed |
| **Wall-E** | **2008** | Animation | 476 | *(scoring…)* | *(scoring…)* | [🇱🇦 Lao](subtitles/Wall-E.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Wall-E.2008.bilingual.srt) | ✓ 28 fixed |

</details>

---

## 🧠 How These Subtitles Are Produced

These subtitles are produced using a local AI translation pipeline running 100% offline on an **NVIDIA GeForce RTX 5090 (32GB VRAM)**, in two stages: generation, then independent verification.

1. **Generation — 5-step cinema translation pass**:
   - **Step 1: Named Entity Recognition & Cultural Pronouns** — Enforces natural honorifics (`ເຈົ້າ`, `ຂ້ອຍ`, `ອ້າຍ`, `ເອື້ອຍ`, `ນ້ອງ`) matched to character relationships.
   - **Step 2: Literal Draft Generation** — Translates dialogue while preserving dramatic tone and pacing.
   - **Step 3: Lao Syntax Alignment** — Normalizes word order, applies correct classifiers (`ໂຕ`, `ຄົນ`, `ຫົວ`, `ຄັນ`), and aligns serial verb constructions (`ເອົາມາ`, `ແລ່ນໜີ`).
   - **Step 4: Spoken Dialogue & Diglossia Pass** — Converts formal written Lao into natural spoken speech (*Phasa Pak*) with authentic pragmatic particles (`ເດີ້`, `ເນາະ`, `ແດ່`).

2. **Fine-Tuned Neural Adapter (LoRA 1.3B Champion)**:
   - Built on Meta's `facebook/nllb-200-distilled-1.3B` architecture.
   - Fine-tuned with Direct Preference Optimization (DPO) on real corrections found during the verification pass below, so mistakes we catch actually get fixed at the model level, not just patched in one file.

3. **Independent verification — the double-lock system**:
   - Described in detail in **How We Verify Quality** above. Every published line is re-generated fresh and checked against the original before anything is trusted.

4. **Frame-Accurate Subtitle Timing**:
   - Audio-aligned with popular release rips (BluRay / BrRip / Sparks / YIFY) with frame-accurate millisecond timestamps.

---

## 📺 How to Use

1. **Download**: Click any `.srt` link above or download from the [website](https://hieng1999.github.io/lao-subtitles/).
2. **Rename**: Rename the `.srt` file to match the exact filename of your movie video file:
   ```
   10.Things.I.Hate.About.You.1999.720p.mkv
   10.Things.I.Hate.About.You.1999.720p.srt
   ```
3. **Play**: Open the video in **VLC**, **MPV**, **Plex**, **IINA**, or **PotPlayer** — the Lao subtitles will automatically appear!
4. **Timing Nudge**: If your release has different opening logos, adjust subtitle delay in VLC by pressing `G` (earlier) or `H` (later).

---

## 🤝 Contributing & Corrections

Native Lao speakers: corrections and feedback are warmly welcomed — and genuinely useful. Automated verification catches a lot (see **How We Verify Quality** above), but it isn't a substitute for a native speaker actually watching a scene.
- Open an **[Issue](https://github.com/Hieng1999/lao-subtitles/issues)** with the movie name, timestamp, and suggested Lao correction.
- Send a **Pull Request** directly with your edits. Corrections feed back into our local AI training data, so a fix you report can improve future movies too, not just the one line.

---

## ❤️ About This Project

This started with a simple wish: to help someone I love enjoy movies in the language they're most comfortable in. Lao subtitles for major films basically don't exist online — so I built a translation pipeline and started making them, and I'm sharing the results here free for anyone to use. If they help even one more family enjoy a movie together, it's worth it.

---

## 📜 License & Disclaimer

Fan-made subtitle translations, shared freely for educational and accessibility purposes. The underlying films and their original dialogue remain © their respective rights holders; this project claims no ownership over the original source media.
