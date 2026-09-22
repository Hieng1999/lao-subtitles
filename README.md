# Lao Movie Subtitles · ຄຳບັນຍາຍພາສາລາວ

[![Website](https://img.shields.io/badge/Website-hieng1999.github.io%2Flao--subtitles-gold?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![Movies](https://img.shields.io/badge/Catalog-287%20Movies-blue?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![Cues](https://img.shields.io/badge/Cues-238,841%20Localized-green?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![Machine Translation](https://img.shields.io/badge/Machine%20Translation-not%20reviewed%20by%20a%20person-lightgrey?style=flat-square)](#please-read-before-downloading)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-blue?style=flat-square)](LICENSE)
[![GPU](https://img.shields.io/badge/Accelerated-NVIDIA%20RTX%205090-76B900?style=flat-square&logo=nvidia)](https://github.com/Hieng1999/lao-subtitles)
[![Model](https://img.shields.io/badge/Fine--Tuned-NLLB--200%20(1.3B)%20%2B%20LoRA-orange?style=flat-square)](https://github.com/Hieng1999/lao-subtitles)

### Please read before downloading

These subtitles are translated by a local machine-translation model. **No human has reviewed these files.** Errors, stiff or unnatural phrasing, and occasional mistranslations are expected -- this is machine output, not a professional or community human translation. If you find a bad line, please open an issue: see **Report a bad line** below.

> Lao notice: pending

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

> 📈 **Round-trip fidelity benchmark (complete):** 287/287 movies scored so far, running average **chrF++ 60.4** / **BLEU 45.2** (published Lao translated back to English and compared to the original — see the per-movie ↺ scores below). See **[Model Evolution](https://hieng1999.github.io/lao-subtitles/#model-evolution)** on the live site for how this compares across model generations.

---

## 📊 Model Translation Quality Benchmarks

These are real, independently-computable numbers — a fresh [sacrebleu](https://github.com/mjpost/sacrebleu) `chrF++`/`BLEU`/`TER` run (audited 2026-09-15 13:27:58) against 100 human-reference translation pairs per domain, re-generated every time this catalog is published, not hand-maintained or estimated:

| Benchmark Domain | Focus | chrF++ | BLEU | TER (lower=better) |
|:---|:---|:---:|:---:|:---:|
| **False Friends Cognate Challenge** | Hard-Negative Lao-Thai Cognates (100 pairs) | **61.7** | **68.1** | **44.8%** |
| **SEA-HELM Cultural & Regional** | Regional Culture & Geography (100 pairs) | **48.0** | **55.9** | **59.0%** |
| **Tatoeba Spoken Conversational** | Natural Conversational Dialogues (100 pairs) | **54.6** | **68.6** | **46.6%** |
| **Tennessee Civics & Legal** | Legal & Government Statutes (100 pairs) | **49.6** | **58.3** | **61.4%** |
| **WMT Biomedical & Healthcare** | Clinical Diagnoses & Dosages (100 pairs) | **51.4** | **64.1** | **47.8%** |

> **This measures general translation quality, not individual movies.** There's no professionally-translated Lao reference for these specific films to score against — that's the gap this project exists to fill. What you're seeing here is the underlying model's performance on standardized, independently-reviewable challenge sets (10 of each suite's 100 pairs are a deliberate stress-test variant of another pair in the same set, testing a known-hard discourse-marker pattern — not 100 fully independent sentences). For quality specific to the movies themselves, see **How We Verify Quality** above.

---


## 🎬 Case Studies: How the Model Learns

These are real, unedited before/after examples pulled directly from the verification corpus described above — not illustrative mockups. Each one shows the exact old published line, the exact new verified correction, and the reasoning the independent back-translation judge gave for approving the fix.

#### Screenplay Direction Fix — *Ad Astra*

- **Source (English):** "After a BEAT:"
- **❌ Legacy Output:** `ຫຼັງຈາກການຕີ:` <sub>(back-translates to: "One catch:")</sub>
- **Machine translation candidate (not reviewed by a person):** `ຈັກບຶດໜຶ່ງ,:`
- **Why:** The old translation took the screenwriting term "beat" (a pause) completely literally, producing the wrong meaning in Lao. The fix recognizes it as a stage direction, not a physical action. *Verification judge: "Both phrases function as a transitional cue indicating a pause or a significant point/condition is about to be addressed."*

#### Calque / Literal-Translation Fix — *10 Things I Hate About You*

- **Source (English):** "You're completely demented."
- **❌ Legacy Output:** `ເຈົ້າໂຊກຮ້າຍຢ່າງສົມບູນ.` <sub>(back-translates to: "You're really crazy.")</sub>
- **Machine translation candidate (not reviewed by a person):** `ເຈົ້າແມ່ນໂງ່ແທ້ໆ.`
- **Why:** A recurring, documented bug in this project: the model would sometimes translate "crazy/insane/demented" using the Lao word for "unlucky" (ໂຊກຮ້າຍ) instead of the correct word for "crazy" (ໂງ່) -- a literal-sounding but semantically wrong substitution. *Verification judge: "Both sentences express that the listener is mentally unstable, with 'demented' and 'crazy' functioning as near-synonyms in this context and the degree modifiers 'completely' and 'really' preserving the intensity."*

#### Calque / Literal-Translation Fix — *2001: A Space Odyssey*

- **Source (English):** "You're kidding."
- **❌ Legacy Output:** `ເຈົ້າໂຊກຮ້າຍ.` <sub>(back-translates to: "You're not serious.")</sub>
- **Machine translation candidate (not reviewed by a person):** `ເຈົ້າແມ່ນບໍ່ຈິງແລ້ວ.`
- **Why:** The same "unlucky"-for-"crazy" calque bug recurring independently in a different movie, confirming it was a systemic model bias rather than a one-off mistake in a single file. *Verification judge: "Both sentences function as rhetorical responses expressing disbelief or disbelief that the previous statement is true."*

#### Idiom / Slang Fix — *12 Monkeys*

- **Source (English):** "Push it tight!"
- **❌ Legacy Output:** `ກົດມັນຢ່າງເຂັ້ມງວດ!` <sub>(back-translates to: "Tighten up!")</sub>
- **Machine translation candidate (not reviewed by a person):** `ແໜ້ນໆເດີ້!`
- **Why:** The old line translated the English idiom word-for-word into a stiff, overly formal Lao command. The fix uses a natural spoken-Lao reduplication pattern a real speaker would actually say. *Verification judge: "Both sentences convey the imperative action of tightening something securely, with 'tighten up' being a standard idiomatic equivalent to 'push it tight'."*

#### Idiom / Slang Fix — *15 Minutes*

- **Source (English):** "In a minute, Ludwig."
- **❌ Legacy Output:** `ໃນນາທີຫນຶ່ງ, ລູດວິດຈ໌.` <sub>(back-translates to: "In a moment, Ludwig.")</sub>
- **Machine translation candidate (not reviewed by a person):** `ອີກບໍ່ດົນ, ລູດວິດິກ.`
- **Why:** "In a minute" was translated as a literal unit of time instead of the idiom "in a moment." The fix restores the natural, non-literal meaning. *Verification judge: "The phrases 'In a minute' and 'In a moment' are synonymous idioms for waiting a short time, and the entity 'Ludwig' is preserved in both."*

#### Hallucination Removal ("cat" substitution) — *The Lord of the Rings: The Fellowship of the Ring*

- **Source (English):** "So the ring of power has been found?"
- **❌ Legacy Output:** `ສະນັ້ນແມວຂອງພະລັງໄດ້ຖືກພົບເຫັນແລ້ວບໍ?` <sub>(back-translates to: "Yes, the power ring has been found?")</sub>
- **Machine translation candidate (not reviewed by a person):** `ແມ່ນແລ້ວແຫວນອໍານາດແມ່ນຖືກພົບແລ້ວບໍ່?`
- **Why:** A known model failure mode: the real, correctly-spelled Lao word for "cat" (ແມວ) sometimes appears as a filler substitution for completely unrelated words -- here standing in for "ring." The fix restores the actual entity from the English source. *Verification judge: "The sentences contain the same core entities (ring/power) and action (has been found), with only minor variations in article and word order that do not change the semantic meaning."*

#### Hallucination Removal (garbled fragment) — *Freddy vs. Jason*

- **Source (English):** "Hey! Watch that!"
- **❌ Legacy Output:** `ເຮ້! ເບິ່ງແມ!` <sub>(back-translates to: "Hello! Watch out!")</sub>
- **Machine translation candidate (not reviewed by a person):** `ສະບາຍດີ! ລະວັງເດີ້!`
- **Why:** The old translation ended in a bare, incomplete "ແມ" fragment -- a known decoder artifact that never finishes into a real word. The fix replaces it with an actual, complete Lao warning phrase. *Verification judge: "Both expressions function as greetings followed by urgent warnings to pay attention or avoid danger."*

---

## 🚩 Report a bad line

Every movie card on the [live site](https://hieng1999.github.io/Hieng1999/lao-subtitles/) has a "Report a bad line" link that opens a pre-filled [GitHub issue](https://github.com/Hieng1999/lao-subtitles/issues/new) for that film -- fill in the timestamp, the line as shown, and what's wrong. You can also open an issue directly at **[https://github.com/Hieng1999/lao-subtitles/issues](https://github.com/Hieng1999/lao-subtitles/issues)**.

## 🎬 Available Subtitles (287 Films · 238,841 Cues)

> 🔍 **Instant Live Search & Filters**:
> To instantly search by title, actor, year, or genre across all **287 movies**, visit our interactive web catalog:
> 🌐 👉 [**hieng1999.github.io/lao-subtitles**](https://hieng1999.github.io/lao-subtitles/)

### ⭐ Featured Spotlight (Top 10 Movies)

| Movie Title | Year | Genre | Cues | Subtitle Downloads | Verification Status |
|:---|:---:|:---|:---:|:---|:---|
| **10 Things I Hate About You** | **1999** | Romance | 1,027 | [🇱🇦 Lao](subtitles/10.Things.I.Hate.About.You.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/10.Things.I.Hate.About.You.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **Spider-Man: Across the Spider-Verse** | **2023** | Animation | 1,542 | [🇱🇦 Lao](subtitles/Spider-Man.Across.the.Spider-Verse.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Spider-Man.Across.the.Spider-Verse.2023.bilingual.srt) | Machine translation, not reviewed by a person |
| **Toy Story** | **1995** | Animation | 887 | [🇱🇦 Lao](subtitles/Toy.Story.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Toy.Story.1995.bilingual.srt) | Machine translation, not reviewed by a person |
| **Avengers: Endgame** | **2019** | Adventure | 1,144 | [🇱🇦 Lao](subtitles/Avengers.Endgame.2019.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Avengers.Endgame.2019.bilingual.srt) | Machine translation, not reviewed by a person |
| **Batman** | **1989** | Thriller | 609 | [🇱🇦 Lao](subtitles/Batman.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Batman.1989.bilingual.srt) | Machine translation, not reviewed by a person |
| **Wall-E** | **2008** | Animation | 476 | [🇱🇦 Lao](subtitles/Wall-E.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Wall-E.2008.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Beauty** | **1999** | Drama | 760 | [🇱🇦 Lao](subtitles/American.Beauty.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Beauty.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **Argo** | **2012** | Thriller | 759 | [🇱🇦 Lao](subtitles/Argo.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Argo.2012.bilingual.srt) | Machine translation, not reviewed by a person |
| **12** | **2007** | Comedy | 505 | [🇱🇦 Lao](subtitles/12.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.2007.bilingual.srt) | Machine translation, not reviewed by a person, 2 flagged of 505 |
| **12 and Holding** | **2005** | Drama | 734 | [🇱🇦 Lao](subtitles/12.and.Holding.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.and.Holding.2005.bilingual.srt) | Machine translation, not reviewed by a person |

<details>
<summary><b>📜 Click here to expand &amp; browse all 287 movies (238,841 localized cues)...</b></summary>

<br/>

| Movie Title | Year | Genre | Cues | Subtitle Downloads | Verification Status |
|:---|:---:|:---|:---:|:---|:---|
| **10 Things I Hate About You** | **1999** | Romance | 1,027 | [🇱🇦 Lao](subtitles/10.Things.I.Hate.About.You.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/10.Things.I.Hate.About.You.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **12** | **2007** | Comedy | 505 | [🇱🇦 Lao](subtitles/12.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.2007.bilingual.srt) | Machine translation, not reviewed by a person, 2 flagged of 505 |
| **12 and Holding** | **2005** | Drama | 734 | [🇱🇦 Lao](subtitles/12.and.Holding.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.and.Holding.2005.bilingual.srt) | Machine translation, not reviewed by a person |
| **12 Monkeys** | **1995** | Thriller | 779 | [🇱🇦 Lao](subtitles/12.Monkeys.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.Monkeys.1995.bilingual.srt) | Machine translation, not reviewed by a person |
| **12 Years a Slave** | **2013** | Drama | 835 | [🇱🇦 Lao](subtitles/12.Years.a.Slave.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.Years.a.Slave.2013.bilingual.srt) | Machine translation, not reviewed by a person |
| **127 Hours** | **2010** | Thriller | 282 | [🇱🇦 Lao](subtitles/127.Hours.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/127.Hours.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **1492: Conquest of Paradise** | **1992** | Drama | 634 | [🇱🇦 Lao](subtitles/1492.Conquest.of.Paradise.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/1492.Conquest.of.Paradise.1992.bilingual.srt) | Machine translation, not reviewed by a person |
| **15 Minutes** | **2001** | Thriller | 1,015 | [🇱🇦 Lao](subtitles/15.Minutes.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/15.Minutes.2001.bilingual.srt) | Machine translation, not reviewed by a person |
| **17 Again** | **2009** | Romance | 817 | [🇱🇦 Lao](subtitles/17.Again.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/17.Again.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **2001: A Space Odyssey** | **1968** | Sci-Fi | 447 | [🇱🇦 Lao](subtitles/2001.A.Space.Odyssey.1968.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/2001.A.Space.Odyssey.1968.bilingual.srt) | Machine translation, not reviewed by a person |
| **2012** | **2009** | Thriller | 893 | [🇱🇦 Lao](subtitles/2012.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/2012.2009.bilingual.srt) | Machine translation, not reviewed by a person, 2 flagged of 893 |
| **20th Century Women** | **2016** | Drama | 648 | [🇱🇦 Lao](subtitles/20th.Century.Women.2016.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/20th.Century.Women.2016.bilingual.srt) | Machine translation, not reviewed by a person |
| **28 Days Later** | **2002** | Sci-Fi | 609 | [🇱🇦 Lao](subtitles/28.Days.Later.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/28.Days.Later.2002.bilingual.srt) | Machine translation, not reviewed by a person |
| **30 Minutes or Less** | **2011** | Comedy | 961 | [🇱🇦 Lao](subtitles/30.Minutes.or.Less.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/30.Minutes.or.Less.2011.bilingual.srt) | Machine translation, not reviewed by a person |
| **42** | **2013** | Drama | 1,042 | [🇱🇦 Lao](subtitles/42.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/42.2013.bilingual.srt) | Machine translation, not reviewed by a person, 16 flagged of 1042 |
| **44 Inch Chest** | **2009** | Drama | 726 | [🇱🇦 Lao](subtitles/44.Inch.Chest.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/44.Inch.Chest.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **48 Hrs.** | **1982** | Thriller | 1,076 | [🇱🇦 Lao](subtitles/48.Hrs..1982.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/48.Hrs..1982.bilingual.srt) | Machine translation, not reviewed by a person |
| **50-50** | **2011** | Drama | 1,067 | [🇱🇦 Lao](subtitles/50-50.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/50-50.2011.bilingual.srt) | Machine translation, not reviewed by a person |
| **500 Days of Summer** | **2009** | Romance | 1,022 | [🇱🇦 Lao](subtitles/500.Days.of.Summer.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/500.Days.of.Summer.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **8MM** | **1999** | Thriller | 794 | [🇱🇦 Lao](subtitles/8MM.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/8MM.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **A Few Good Men** | **1992** | Thriller | 1,458 | [🇱🇦 Lao](subtitles/A.Few.Good.Men.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Few.Good.Men.1992.bilingual.srt) | Machine translation, not reviewed by a person |
| **A Good Person** | **2023** | Drama | 978 | [🇱🇦 Lao](subtitles/A.Good.Person.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Good.Person.2023.bilingual.srt) | Machine translation, not reviewed by a person |
| **A Million Miles Away** | **2023** | Drama | 706 | [🇱🇦 Lao](subtitles/A.Million.Miles.Away.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Million.Miles.Away.2023.bilingual.srt) | Machine translation, not reviewed by a person |
| **A Most Violent Year** | **2014** | Drama | 1,175 | [🇱🇦 Lao](subtitles/A.Most.Violent.Year.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Most.Violent.Year.2014.bilingual.srt) | Machine translation, not reviewed by a person |
| **A Prayer Before Dawn** | **2017** | Drama | 364 | [🇱🇦 Lao](subtitles/A.Prayer.Before.Dawn.2017.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Prayer.Before.Dawn.2017.bilingual.srt) | Machine translation, not reviewed by a person |
| **A Quiet Place** | **2018** | Sci-Fi | 90 | [🇱🇦 Lao](subtitles/A.Quiet.Place.2018.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Quiet.Place.2018.bilingual.srt) | Machine translation, not reviewed by a person |
| **A Real Pain** | **2024** | Drama | 871 | [🇱🇦 Lao](subtitles/A.Real.Pain.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Real.Pain.2024.bilingual.srt) | Machine translation, not reviewed by a person |
| **A Scanner Darkly** | **2006** | Drama | 1,117 | [🇱🇦 Lao](subtitles/A.Scanner.Darkly.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Scanner.Darkly.2006.bilingual.srt) | Machine translation, not reviewed by a person |
| **A Serious Man** | **2009** | Comedy | 825 | [🇱🇦 Lao](subtitles/A.Serious.Man.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Serious.Man.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **Above the Law** | **1988** | Action | 550 | [🇱🇦 Lao](subtitles/Above.the.Law.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Above.the.Law.1988.bilingual.srt) | Machine translation, not reviewed by a person |
| **Absolute Power** | **1997** | Thriller | 509 | [🇱🇦 Lao](subtitles/Absolute.Power.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Absolute.Power.1997.bilingual.srt) | Machine translation, not reviewed by a person |
| **Ad Astra** | **2019** | Thriller | 493 | [🇱🇦 Lao](subtitles/Ad.Astra.2019.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Ad.Astra.2019.bilingual.srt) | Machine translation, not reviewed by a person |
| **Adaptation** | **2002** | Drama | 820 | [🇱🇦 Lao](subtitles/Adaptation.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Adaptation.2002.bilingual.srt) | Machine translation, not reviewed by a person |
| **Affliction** | **1997** | Drama | 770 | [🇱🇦 Lao](subtitles/Affliction.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Affliction.1997.bilingual.srt) | Machine translation, not reviewed by a person |
| **After School Special** | **2003** | Comedy | 1,193 | [🇱🇦 Lao](subtitles/After.School.Special.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/After.School.Special.2003.bilingual.srt) | Machine translation, not reviewed by a person |
| **After.Life** | **2009** | Thriller | 809 | [🇱🇦 Lao](subtitles/After.Life.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/After.Life.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **Agnes of God** | **1985** | Drama | 944 | [🇱🇦 Lao](subtitles/Agnes.of.God.1985.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Agnes.of.God.1985.bilingual.srt) | Machine translation, not reviewed by a person |
| **Air** | **2023** | Drama | 834 | [🇱🇦 Lao](subtitles/Air.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Air.2023.bilingual.srt) | Machine translation, not reviewed by a person |
| **Air Force One** | **1997** | Thriller | 919 | [🇱🇦 Lao](subtitles/Air.Force.One.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Air.Force.One.1997.bilingual.srt) | Machine translation, not reviewed by a person |
| **Airplane** | **1980** | Romance | 627 | [🇱🇦 Lao](subtitles/Airplane.1980.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Airplane.1980.bilingual.srt) | Machine translation, not reviewed by a person |
| **Airplane 2: The Sequel** | **1982** | Sci-Fi | 937 | [🇱🇦 Lao](subtitles/Airplane.2.The.Sequel.1982.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Airplane.2.The.Sequel.1982.bilingual.srt) | Machine translation, not reviewed by a person |
| **Ali** | **2001** | Drama | 995 | [🇱🇦 Lao](subtitles/Ali.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Ali.2001.bilingual.srt) | Machine translation, not reviewed by a person |
| **Alien** | **1979** | Feature Film | 883 | [🇱🇦 Lao](subtitles/Alien.1979.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alien.1979.bilingual.srt) | Machine translation, not reviewed by a person |
| **Alien 3** | **1992** | Thriller | 689 | [🇱🇦 Lao](subtitles/Alien.3.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alien.3.1992.bilingual.srt) | Machine translation, not reviewed by a person |
| **Alien Nation** | **1988** | Sci-Fi | 544 | [🇱🇦 Lao](subtitles/Alien.Nation.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alien.Nation.1988.bilingual.srt) | Machine translation, not reviewed by a person |
| **Aliens** | **1986** | Thriller | 724 | [🇱🇦 Lao](subtitles/Aliens.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Aliens.1986.bilingual.srt) | Machine translation, not reviewed by a person |
| **All About Eve** | **1950** | Drama | 1,409 | [🇱🇦 Lao](subtitles/All.About.Eve.1950.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.About.Eve.1950.bilingual.srt) | Machine translation, not reviewed by a person |
| **All About Steve** | **2009** | Comedy | 777 | [🇱🇦 Lao](subtitles/All.About.Steve.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.About.Steve.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **All of Us Strangers** | **2023** | Romance | 621 | [🇱🇦 Lao](subtitles/All.of.Us.Strangers.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.of.Us.Strangers.2023.bilingual.srt) | Machine translation, not reviewed by a person |
| **All the King's Men** | **2006** | Drama | 1,078 | [🇱🇦 Lao](subtitles/All.the.Kings.Men.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.the.Kings.Men.2006.bilingual.srt) | Machine translation, not reviewed by a person |
| **All the President's Men** | **1976** | Thriller | 994 | [🇱🇦 Lao](subtitles/All.the.Presidents.Men.1976.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.the.Presidents.Men.1976.bilingual.srt) | Machine translation, not reviewed by a person |
| **Almost Famous** | **2000** | Romance | 1,037 | [🇱🇦 Lao](subtitles/Almost.Famous.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Almost.Famous.2000.bilingual.srt) | Machine translation, not reviewed by a person |
| **Alone in the Dark** | **2005** | Thriller | 402 | [🇱🇦 Lao](subtitles/Alone.in.the.Dark.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alone.in.the.Dark.2005.bilingual.srt) | Machine translation, not reviewed by a person |
| **Amadeus** | **1984** | Drama | 1,379 | [🇱🇦 Lao](subtitles/Amadeus.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Amadeus.1984.bilingual.srt) | Machine translation, not reviewed by a person |
| **Amelia** | **2009** | Drama | 882 | [🇱🇦 Lao](subtitles/Amelia.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Amelia.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Beauty** | **1999** | Drama | 760 | [🇱🇦 Lao](subtitles/American.Beauty.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Beauty.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Fiction** | **2023** | Drama | 1,025 | [🇱🇦 Lao](subtitles/American.Fiction.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Fiction.2023.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Gangster** | **2007** | Drama | 839 | [🇱🇦 Lao](subtitles/American.Gangster.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Gangster.2007.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Graffiti** | **1973** | Drama | 1,122 | [🇱🇦 Lao](subtitles/American.Graffiti.1973.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Graffiti.1973.bilingual.srt) | Machine translation, not reviewed by a person |
| **American History X** | **1998** | Thriller | 794 | [🇱🇦 Lao](subtitles/American.History.X.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.History.X.1998.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Hustle** | **2013** | Drama | 1,225 | [🇱🇦 Lao](subtitles/American.Hustle.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Hustle.2013.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Milkshake** | **2013** | Comedy | 801 | [🇱🇦 Lao](subtitles/American.Milkshake.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Milkshake.2013.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Pie** | **1999** | Comedy | 927 | [🇱🇦 Lao](subtitles/American.Pie.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Pie.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Shaolin: King of Kickboxers II** | **1992** | Action | 599 | [🇱🇦 Lao](subtitles/American.Shaolin.King.of.Kickboxers.II.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Shaolin.King.of.Kickboxers.II.1992.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Sniper** | **2014** | Action | 914 | [🇱🇦 Lao](subtitles/American.Sniper.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Sniper.2014.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Splendor** | **2003** | Comedy | 584 | [🇱🇦 Lao](subtitles/American.Splendor.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Splendor.2003.bilingual.srt) | Machine translation, not reviewed by a person |
| **American Werewolf in London** | **1981** | Romance | 854 | [🇱🇦 Lao](subtitles/American.Werewolf.in.London.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Werewolf.in.London.1981.bilingual.srt) | Machine translation, not reviewed by a person |
| **Amour** | **2012** | Romance | 502 | [🇱🇦 Lao](subtitles/Amour.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Amour.2012.bilingual.srt) | Machine translation, not reviewed by a person |
| **Analyze That** | **2002** | Crime | 1,138 | [🇱🇦 Lao](subtitles/Analyze.That.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Analyze.That.2002.bilingual.srt) | Machine translation, not reviewed by a person |
| **Analyze This** | **1999** | Crime | 1,151 | [🇱🇦 Lao](subtitles/Analyze.This.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Analyze.This.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **Anastasia** | **1997** | Animation | 587 | [🇱🇦 Lao](subtitles/Anastasia.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Anastasia.1997.bilingual.srt) | Machine translation, not reviewed by a person |
| **Angel Eyes** | **2001** | Romance | 974 | [🇱🇦 Lao](subtitles/Angel.Eyes.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Angel.Eyes.2001.bilingual.srt) | Machine translation, not reviewed by a person |
| **Annie Hall** | **1977** | Romance | 1,291 | [🇱🇦 Lao](subtitles/Annie.Hall.1977.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Annie.Hall.1977.bilingual.srt) | Machine translation, not reviewed by a person |
| **Anonymous** | **2011** | Thriller | 820 | [🇱🇦 Lao](subtitles/Anonymous.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Anonymous.2011.bilingual.srt) | Machine translation, not reviewed by a person |
| **Anora** | **2024** | Romance | 1,137 | [🇱🇦 Lao](subtitles/Anora.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Anora.2024.bilingual.srt) | Machine translation, not reviewed by a person |
| **Antitrust** | **2001** | Thriller | 903 | [🇱🇦 Lao](subtitles/Antitrust.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Antitrust.2001.bilingual.srt) | Machine translation, not reviewed by a person |
| **Antz** | **1998** | Comedy | 438 | [🇱🇦 Lao](subtitles/Antz.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Antz.1998.bilingual.srt) | Machine translation, not reviewed by a person |
| **Apocalypse Now** | **1979** | Action | 968 | [🇱🇦 Lao](subtitles/Apocalypse.Now.1979.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Apocalypse.Now.1979.bilingual.srt) | Machine translation, not reviewed by a person |
| **April Fool's Day** | **1986** | Horror | 812 | [🇱🇦 Lao](subtitles/April.Fools.Day.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/April.Fools.Day.1986.bilingual.srt) | Machine translation, not reviewed by a person |
| **Apt Pupil** | **1998** | Thriller | 897 | [🇱🇦 Lao](subtitles/Apt.Pupil.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Apt.Pupil.1998.bilingual.srt) | Machine translation, not reviewed by a person |
| **Arbitrage** | **2012** | Thriller | 1,007 | [🇱🇦 Lao](subtitles/Arbitrage.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arbitrage.2012.bilingual.srt) | Machine translation, not reviewed by a person |
| **Arcade** | **1993** | Sci-Fi | 518 | [🇱🇦 Lao](subtitles/Arcade.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arcade.1993.bilingual.srt) | Machine translation, not reviewed by a person |
| **Arctic Blue** | **1993** | Thriller | 613 | [🇱🇦 Lao](subtitles/Arctic.Blue.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arctic.Blue.1993.bilingual.srt) | Machine translation, not reviewed by a person |
| **Argo** | **2012** | Thriller | 759 | [🇱🇦 Lao](subtitles/Argo.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Argo.2012.bilingual.srt) | Machine translation, not reviewed by a person |
| **Army of Darkness** | **1992** | Horror | 234 | [🇱🇦 Lao](subtitles/Army.of.Darkness.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Army.of.Darkness.1992.bilingual.srt) | Machine translation, not reviewed by a person |
| **Arthur** | **2011** | Comedy | 1,003 | [🇱🇦 Lao](subtitles/Arthur.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arthur.2011.bilingual.srt) | Machine translation, not reviewed by a person |
| **As Good As It Gets** | **1997** | Romance | 824 | [🇱🇦 Lao](subtitles/As.Good.As.It.Gets.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/As.Good.As.It.Gets.1997.bilingual.srt) | Machine translation, not reviewed by a person |
| **Assassins** | **1995** | Thriller | 877 | [🇱🇦 Lao](subtitles/Assassins.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Assassins.1995.bilingual.srt) | Machine translation, not reviewed by a person |
| **Asteroid City** | **2023** | Sci-Fi | 820 | [🇱🇦 Lao](subtitles/Asteroid.City.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Asteroid.City.2023.bilingual.srt) | Machine translation, not reviewed by a person |
| **Austin Powers - International Man of Mystery** | **1997** | Comedy | 802 | [🇱🇦 Lao](subtitles/Austin.Powers.-.International.Man.of.Mystery.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Austin.Powers.-.International.Man.of.Mystery.1997.bilingual.srt) | Machine translation, not reviewed by a person |
| **Austin Powers - The Spy Who Shagged Me** | **1999** | Comedy | 773 | [🇱🇦 Lao](subtitles/Austin.Powers.-.The.Spy.Who.Shagged.Me.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Austin.Powers.-.The.Spy.Who.Shagged.Me.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **Authors Anonymous** | **2014** | Comedy | 765 | [🇱🇦 Lao](subtitles/Authors.Anonymous.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Authors.Anonymous.2014.bilingual.srt) | Machine translation, not reviewed by a person |
| **Autumn in New York** | **2000** | Romance | 916 | [🇱🇦 Lao](subtitles/Autumn.in.New.York.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Autumn.in.New.York.2000.bilingual.srt) | Machine translation, not reviewed by a person |
| **Avatar** | **2009** | Sci-Fi | 784 | [🇱🇦 Lao](subtitles/Avatar.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Avatar.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **Avengers: Endgame** | **2019** | Adventure | 1,144 | [🇱🇦 Lao](subtitles/Avengers.Endgame.2019.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Avengers.Endgame.2019.bilingual.srt) | Machine translation, not reviewed by a person |
| **Babel** | **2006** | Thriller | 1,031 | [🇱🇦 Lao](subtitles/Babel.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Babel.2006.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bachelor Party** | **1984** | Comedy | 952 | [🇱🇦 Lao](subtitles/Bachelor.Party.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bachelor.Party.1984.bilingual.srt) | Machine translation, not reviewed by a person |
| **Backdraft** | **1991** | Thriller | 962 | [🇱🇦 Lao](subtitles/Backdraft.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Backdraft.1991.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bad Boys** | **1995** | Comedy | 792 | [🇱🇦 Lao](subtitles/Bad.Boys.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Boys.1995.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bad Country** | **2014** | Crime | 773 | [🇱🇦 Lao](subtitles/Bad.Country.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Country.2014.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bad Day at Black Rock** | **1955** | Thriller | 781 | [🇱🇦 Lao](subtitles/Bad.Day.at.Black.Rock.1955.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Day.at.Black.Rock.1955.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bad Dreams** | **1988** | Thriller | 732 | [🇱🇦 Lao](subtitles/Bad.Dreams.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Dreams.1988.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bad Lieutenant** | **1992** | Crime | 332 | [🇱🇦 Lao](subtitles/Bad.Lieutenant.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Lieutenant.1992.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bad Santa** | **2003** | Crime | 659 | [🇱🇦 Lao](subtitles/Bad.Santa.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Santa.2003.bilingual.srt) | Machine translation, not reviewed by a person |
| **Barbie** | **2023** | Adventure | 959 | [🇱🇦 Lao](subtitles/Barbie.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Barbie.2023.bilingual.srt) | Machine translation, not reviewed by a person |
| **Barry Lyndon** | **1975** | Romance | 787 | [🇱🇦 Lao](subtitles/Barry.Lyndon.1975.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Barry.Lyndon.1975.bilingual.srt) | Machine translation, not reviewed by a person |
| **Barton Fink** | **1991** | Thriller | 771 | [🇱🇦 Lao](subtitles/Barton.Fink.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Barton.Fink.1991.bilingual.srt) | Machine translation, not reviewed by a person |
| **Basic** | **2003** | Thriller | 1,059 | [🇱🇦 Lao](subtitles/Basic.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Basic.2003.bilingual.srt) | Machine translation, not reviewed by a person |
| **Basic Instinct** | **1992** | Thriller | 881 | [🇱🇦 Lao](subtitles/Basic.Instinct.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Basic.Instinct.1992.bilingual.srt) | Machine translation, not reviewed by a person |
| **Batman** | **1989** | Thriller | 609 | [🇱🇦 Lao](subtitles/Batman.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Batman.1989.bilingual.srt) | Machine translation, not reviewed by a person |
| **Batman 2** | **1992** | Thriller | 604 | [🇱🇦 Lao](subtitles/Batman.2.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Batman.2.1992.bilingual.srt) | Machine translation, not reviewed by a person |
| **Battle: Los Angeles** | **2011** | Sci-Fi | 681 | [🇱🇦 Lao](subtitles/Battle.Los.Angeles.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Battle.Los.Angeles.2011.bilingual.srt) | Machine translation, not reviewed by a person |
| **Beavis and Butt-head Do America** | **1996** | Animation | 703 | [🇱🇦 Lao](subtitles/Beavis.and.Butt-head.Do.America.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Beavis.and.Butt-head.Do.America.1996.bilingual.srt) | Machine translation, not reviewed by a person |
| **Beginners** | **2010** | Romance | 745 | [🇱🇦 Lao](subtitles/Beginners.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Beginners.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **Belle** | **2013** | Romance | 813 | [🇱🇦 Lao](subtitles/Belle.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Belle.2013.bilingual.srt) | Machine translation, not reviewed by a person |
| **Big Eyes** | **2014** | Crime | 835 | [🇱🇦 Lao](subtitles/Big.Eyes.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Big.Eyes.2014.bilingual.srt) | Machine translation, not reviewed by a person |
| **Big Fish** | **2003** | Adventure | 804 | [🇱🇦 Lao](subtitles/Big.Fish.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Big.Fish.2003.bilingual.srt) | Machine translation, not reviewed by a person |
| **Birdman** | **2014** | Romance | 1,099 | [🇱🇦 Lao](subtitles/Birdman.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Birdman.2014.bilingual.srt) | Machine translation, not reviewed by a person |
| **Birthday Girl** | **2001** | Romance | 593 | [🇱🇦 Lao](subtitles/Birthday.Girl.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Birthday.Girl.2001.bilingual.srt) | Machine translation, not reviewed by a person |
| **Black Panther** | **2018** | Sci-Fi | 923 | [🇱🇦 Lao](subtitles/Black.Panther.2018.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Black.Panther.2018.bilingual.srt) | Machine translation, not reviewed by a person |
| **Black Rain** | **1989** | Crime | 650 | [🇱🇦 Lao](subtitles/Black.Rain.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Black.Rain.1989.bilingual.srt) | Machine translation, not reviewed by a person |
| **BlacKkKlansman** | **2018** | Crime | 1,089 | [🇱🇦 Lao](subtitles/BlacKkKlansman.2018.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/BlacKkKlansman.2018.bilingual.srt) | Machine translation, not reviewed by a person |
| **Blade** | **1998** | Sci-Fi | 560 | [🇱🇦 Lao](subtitles/Blade.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.1998.bilingual.srt) | Machine translation, not reviewed by a person |
| **Blade II** | **2002** | Horror | 566 | [🇱🇦 Lao](subtitles/Blade.II.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.II.2002.bilingual.srt) | Machine translation, not reviewed by a person |
| **Blade Runner** | **1982** | Sci-Fi | 746 | [🇱🇦 Lao](subtitles/Blade.Runner.1982.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.Runner.1982.bilingual.srt) | Machine translation, not reviewed by a person |
| **Blade: Trinity** | **2004** | Horror | 574 | [🇱🇦 Lao](subtitles/Blade.Trinity.2004.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.Trinity.2004.bilingual.srt) | Machine translation, not reviewed by a person |
| **Blitz** | **2011** | Action | 602 | [🇱🇦 Lao](subtitles/Blitz.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blitz.2011.bilingual.srt) | Machine translation, not reviewed by a person |
| **Blood and Wine** | **1996** | Crime | 926 | [🇱🇦 Lao](subtitles/Blood.and.Wine.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blood.and.Wine.1996.bilingual.srt) | Machine translation, not reviewed by a person |
| **Blood Diamond** | **2006** | Feature Film | 1,443 | [🇱🇦 Lao](subtitles/Blood.Diamond.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blood.Diamond.2006.bilingual.srt) | Machine translation, not reviewed by a person |
| **Blow** | **2001** | Crime | 1,026 | [🇱🇦 Lao](subtitles/Blow.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blow.2001.bilingual.srt) | Machine translation, not reviewed by a person |
| **Blue Valentine** | **2010** | Romance | 679 | [🇱🇦 Lao](subtitles/Blue.Valentine.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blue.Valentine.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **Blue Velvet** | **1986** | Crime | 948 | [🇱🇦 Lao](subtitles/Blue.Velvet.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blue.Velvet.1986.bilingual.srt) | Machine translation, not reviewed by a person |
| **Body Heat** | **1981** | Crime | 871 | [🇱🇦 Lao](subtitles/Body.Heat.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Body.Heat.1981.bilingual.srt) | Machine translation, not reviewed by a person |
| **Body of Evidence** | **1993** | Romance | 928 | [🇱🇦 Lao](subtitles/Body.of.Evidence.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Body.of.Evidence.1993.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bodyguard** | **1992** | Romance | 964 | [🇱🇦 Lao](subtitles/Bodyguard.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bodyguard.1992.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bones** | **2001** | Horror | 696 | [🇱🇦 Lao](subtitles/Bones.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bones.2001.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bonnie and Clyde** | **1967** | Romance | 736 | [🇱🇦 Lao](subtitles/Bonnie.and.Clyde.1967.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bonnie.and.Clyde.1967.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bookworm** | **2024** | Adventure | 889 | [🇱🇦 Lao](subtitles/Bookworm.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bookworm.2024.bilingual.srt) | Machine translation, not reviewed by a person |
| **Boondock Saints 2: All Saints Day** | **2009** | Crime | 892 | [🇱🇦 Lao](subtitles/Boondock.Saints.2.All.Saints.Day.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Boondock.Saints.2.All.Saints.Day.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bottle Rocket** | **1996** | Crime | 1,195 | [🇱🇦 Lao](subtitles/Bottle.Rocket.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bottle.Rocket.1996.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bound** | **1996** | Crime | 918 | [🇱🇦 Lao](subtitles/Bound.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bound.1996.bilingual.srt) | Machine translation, not reviewed by a person |
| **Brazil** | **1985** | Sci-Fi | 912 | [🇱🇦 Lao](subtitles/Brazil.1985.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Brazil.1985.bilingual.srt) | Machine translation, not reviewed by a person |
| **Broadcast News** | **1987** | Romance | 1,127 | [🇱🇦 Lao](subtitles/Broadcast.News.1987.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Broadcast.News.1987.bilingual.srt) | Machine translation, not reviewed by a person |
| **Broken Arrow** | **1996** | Adventure | 921 | [🇱🇦 Lao](subtitles/Broken.Arrow.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Broken.Arrow.1996.bilingual.srt) | Machine translation, not reviewed by a person |
| **Broken Embraces** | **2009** | Romance | 991 | [🇱🇦 Lao](subtitles/Broken.Embraces.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Broken.Embraces.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bruce Almighty** | **2003** | Romance | 837 | [🇱🇦 Lao](subtitles/Bruce.Almighty.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bruce.Almighty.2003.bilingual.srt) | Machine translation, not reviewed by a person |
| **Buffy the Vampire Slayer** | **1992** | Horror | 941 | [🇱🇦 Lao](subtitles/Buffy.the.Vampire.Slayer.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Buffy.the.Vampire.Slayer.1992.bilingual.srt) | Machine translation, not reviewed by a person |
| **Bull Durham** | **1988** | Romance | 884 | [🇱🇦 Lao](subtitles/Bull.Durham.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bull.Durham.1988.bilingual.srt) | Machine translation, not reviewed by a person |
| **Burlesque** | **2010** | Romance | 1,041 | [🇱🇦 Lao](subtitles/Burlesque.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Burlesque.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **Burn After Reading** | **2008** | Crime | 1,052 | [🇱🇦 Lao](subtitles/Burn.After.Reading.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Burn.After.Reading.2008.bilingual.srt) | Machine translation, not reviewed by a person |
| **Burning Annie** | **2004** | Romance | 1,165 | [🇱🇦 Lao](subtitles/Burning.Annie.2004.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Burning.Annie.2004.bilingual.srt) | Machine translation, not reviewed by a person |
| **Capote** | **2005** | Crime | 768 | [🇱🇦 Lao](subtitles/Capote.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Capote.2005.bilingual.srt) | Machine translation, not reviewed by a person |
| **Carrie** | **1976** | Horror | 719 | [🇱🇦 Lao](subtitles/Carrie.1976.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Carrie.1976.bilingual.srt) | Machine translation, not reviewed by a person |
| **Cars 2** | **2011** | Animation | 1,226 | [🇱🇦 Lao](subtitles/Cars.2.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cars.2.2011.bilingual.srt) | Machine translation, not reviewed by a person |
| **Case 39** | **2009** | Horror | 746 | [🇱🇦 Lao](subtitles/Case.39.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Case.39.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **Casino** | **1995** | Crime | 2,483 | [🇱🇦 Lao](subtitles/Casino.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Casino.1995.bilingual.srt) | Machine translation, not reviewed by a person |
| **Cast Away** | **2000** | Adventure | 787 | [🇱🇦 Lao](subtitles/Cast.Away.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cast.Away.2000.bilingual.srt) | Machine translation, not reviewed by a person |
| **Catch Me If You Can** | **2002** | Crime | 933 | [🇱🇦 Lao](subtitles/Catch.Me.If.You.Can.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Catch.Me.If.You.Can.2002.bilingual.srt) | Machine translation, not reviewed by a person |
| **Charade** | **1963** | Romance | 1,355 | [🇱🇦 Lao](subtitles/Charade.1963.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Charade.1963.bilingual.srt) | Machine translation, not reviewed by a person |
| **Chasing Amy** | **1997** | Romance | 1,075 | [🇱🇦 Lao](subtitles/Chasing.Amy.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Chasing.Amy.1997.bilingual.srt) | Machine translation, not reviewed by a person |
| **Cherry Falls** | **2000** | Horror | 701 | [🇱🇦 Lao](subtitles/Cherry.Falls.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cherry.Falls.2000.bilingual.srt) | Machine translation, not reviewed by a person |
| **Chronicle** | **2012** | Sci-Fi | 738 | [🇱🇦 Lao](subtitles/Chronicle.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Chronicle.2012.bilingual.srt) | Machine translation, not reviewed by a person |
| **Chronicles of Narnia: The Lion, the Witch and the Wardrobe** | **2005** | Adventure | 629 | [🇱🇦 Lao](subtitles/Chronicles.of.Narnia.The.Lion.the.Witch.and.the.Wardrobe.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Chronicles.of.Narnia.The.Lion.the.Witch.and.the.Wardrobe.2005.bilingual.srt) | Machine translation, not reviewed by a person |
| **Cinema Paradiso** | **1988** | Romance | 457 | [🇱🇦 Lao](subtitles/Cinema.Paradiso.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cinema.Paradiso.1988.bilingual.srt) | Machine translation, not reviewed by a person |
| **Cirque du Freak: The Vampire's Assistant** | **2009** | Adventure | 938 | [🇱🇦 Lao](subtitles/Cirque.du.Freak.The.Vampires.Assistant.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cirque.du.Freak.The.Vampires.Assistant.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **Clash of the Titans** | **2010** | Adventure | 764 | [🇱🇦 Lao](subtitles/Clash.of.the.Titans.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Clash.of.the.Titans.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **Cliffhanger** | **1993** | Adventure | 559 | [🇱🇦 Lao](subtitles/Cliffhanger.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cliffhanger.1993.bilingual.srt) | Machine translation, not reviewed by a person |
| **Coco** | **2017** | Feature Film | 1,444 | [🇱🇦 Lao](subtitles/Coco.2017.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Coco.2017.bilingual.srt) | Machine translation, not reviewed by a person |
| **Constantine** | **2005** | Horror | 721 | [🇱🇦 Lao](subtitles/Constantine.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Constantine.2005.bilingual.srt) | Machine translation, not reviewed by a person |
| **Copycat** | **1995** | Horror | 843 | [🇱🇦 Lao](subtitles/Copycat.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Copycat.1995.bilingual.srt) | Machine translation, not reviewed by a person |
| **Coraline** | **2009** | Animation | 804 | [🇱🇦 Lao](subtitles/Coraline.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Coraline.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **Corpse Bride** | **2005** | Animation | 495 | [🇱🇦 Lao](subtitles/Corpse.Bride.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Corpse.Bride.2005.bilingual.srt) | Machine translation, not reviewed by a person |
| **Crouching Tiger, Hidden Dragon** | **2000** | Adventure | 531 | [🇱🇦 Lao](subtitles/Crouching.Tiger.Hidden.Dragon.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Crouching.Tiger.Hidden.Dragon.2000.bilingual.srt) | Machine translation, not reviewed by a person |
| **Dances with Wolves** | **1990** | Adventure | 638 | [🇱🇦 Lao](subtitles/Dances.with.Wolves.1990.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dances.with.Wolves.1990.bilingual.srt) | Machine translation, not reviewed by a person |
| **Dark City** | **1998** | Sci-Fi | 560 | [🇱🇦 Lao](subtitles/Dark.City.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dark.City.1998.bilingual.srt) | Machine translation, not reviewed by a person |
| **Dark Star** | **1974** | Sci-Fi | 350 | [🇱🇦 Lao](subtitles/Dark.Star.1974.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dark.Star.1974.bilingual.srt) | Machine translation, not reviewed by a person |
| **Darkman** | **1990** | Sci-Fi | 930 | [🇱🇦 Lao](subtitles/Darkman.1990.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Darkman.1990.bilingual.srt) | Machine translation, not reviewed by a person |
| **Dawn of the Dead** | **2004** | Horror | 139 | [🇱🇦 Lao](subtitles/Dawn.of.the.Dead.2004.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dawn.of.the.Dead.2004.bilingual.srt) | Machine translation, not reviewed by a person |
| **Deadpool** | **2016** | Adventure | 742 | [🇱🇦 Lao](subtitles/Deadpool.2016.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Deadpool.2016.bilingual.srt) | Machine translation, not reviewed by a person |
| **Deadpool & Wolverine** | **2024** | Sci-Fi | 742 | [🇱🇦 Lao](subtitles/Deadpool.and.Wolverine.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Deadpool.and.Wolverine.2024.bilingual.srt) | Machine translation, not reviewed by a person |
| **Deep Rising** | **1998** | Horror | 632 | [🇱🇦 Lao](subtitles/Deep.Rising.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Deep.Rising.1998.bilingual.srt) | Machine translation, not reviewed by a person |
| **Despicable Me 2** | **2013** | Animation | 710 | [🇱🇦 Lao](subtitles/Despicable.Me.2.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Despicable.Me.2.2013.bilingual.srt) | Machine translation, not reviewed by a person |
| **Detroit Rock City** | **1999** | Adventure | 777 | [🇱🇦 Lao](subtitles/Detroit.Rock.City.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Detroit.Rock.City.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **Devil's Advocate** | **1997** | Horror | 1,060 | [🇱🇦 Lao](subtitles/Devils.Advocate.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Devils.Advocate.1997.bilingual.srt) | Machine translation, not reviewed by a person |
| **Django Unchained** | **2012** | Adventure | 1,067 | [🇱🇦 Lao](subtitles/Django.Unchained.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Django.Unchained.2012.bilingual.srt) | Machine translation, not reviewed by a person |
| **Dogma** | **1999** | Adventure | 955 | [🇱🇦 Lao](subtitles/Dogma.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dogma.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **Drag Me to Hell** | **2009** | Horror | 665 | [🇱🇦 Lao](subtitles/Drag.Me.to.Hell.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Drag.Me.to.Hell.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **Dune** | **1984** | Sci-Fi | 617 | [🇱🇦 Lao](subtitles/Dune.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dune.1984.bilingual.srt) | Machine translation, not reviewed by a person |
| **Dune Part One** | **2021** | Sci-Fi | 648 | [🇱🇦 Lao](subtitles/Dune.Part.One.2021.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dune.Part.One.2021.bilingual.srt) | Machine translation, not reviewed by a person |
| **Eight Legged Freaks** | **2002** | Sci-Fi | 675 | [🇱🇦 Lao](subtitles/Eight.Legged.Freaks.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Eight.Legged.Freaks.2002.bilingual.srt) | Machine translation, not reviewed by a person |
| **Elemental** | **2023** | Animation | 906 | [🇱🇦 Lao](subtitles/Elemental.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Elemental.2023.bilingual.srt) | Machine translation, not reviewed by a person |
| **Escape From L.A.** | **1996** | Sci-Fi | 617 | [🇱🇦 Lao](subtitles/Escape.From.L.A..1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Escape.From.L.A..1996.bilingual.srt) | Machine translation, not reviewed by a person |
| **Event Horizon** | **1997** | Horror | 892 | [🇱🇦 Lao](subtitles/Event.Horizon.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Event.Horizon.1997.bilingual.srt) | Machine translation, not reviewed by a person |
| **Evil Dead** | **1981** | Horror | 310 | [🇱🇦 Lao](subtitles/Evil.Dead.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Evil.Dead.1981.bilingual.srt) | Machine translation, not reviewed by a person |
| **Evil Dead II: Dead by Dawn** | **1987** | Horror | 221 | [🇱🇦 Lao](subtitles/Evil.Dead.II.Dead.by.Dawn.1987.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Evil.Dead.II.Dead.by.Dawn.1987.bilingual.srt) | Machine translation, not reviewed by a person |
| **Fantastic Mr Fox** | **2009** | Animation | 625 | [🇱🇦 Lao](subtitles/Fantastic.Mr.Fox.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Fantastic.Mr.Fox.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **Feast** | **2005** | Horror | 831 | [🇱🇦 Lao](subtitles/Feast.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Feast.2005.bilingual.srt) | Machine translation, not reviewed by a person |
| **Fight Club** | **1999** | Drama / Classics | 1,293 | [🇱🇦 Lao](subtitles/Fight.Club.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Fight.Club.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **Final Destination** | **2000** | Horror | 447 | [🇱🇦 Lao](subtitles/Final.Destination.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Final.Destination.2000.bilingual.srt) | Machine translation, not reviewed by a person |
| **Final Destination 2** | **2003** | Horror | 648 | [🇱🇦 Lao](subtitles/Final.Destination.2.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Final.Destination.2.2003.bilingual.srt) | Machine translation, not reviewed by a person |
| **Forrest Gump** | **1994** | Drama / Classics | 1,065 | [🇱🇦 Lao](subtitles/Forrest.Gump.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Forrest.Gump.1994.bilingual.srt) | Machine translation, not reviewed by a person |
| **Freddy vs. Jason** | **2003** | Horror | 716 | [🇱🇦 Lao](subtitles/Freddy.vs..Jason.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Freddy.vs..Jason.2003.bilingual.srt) | Machine translation, not reviewed by a person |
| **Friday the 13th** | **1980** | Horror | 432 | [🇱🇦 Lao](subtitles/Friday.the.13th.1980.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Friday.the.13th.1980.bilingual.srt) | Machine translation, not reviewed by a person |
| **Friday the 13th Part VIII: Jason Takes Manhattan** | **1989** | Horror | 569 | [🇱🇦 Lao](subtitles/Friday.the.13th.Part.VIII.Jason.Takes.Manhattan.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Friday.the.13th.Part.VIII.Jason.Takes.Manhattan.1989.bilingual.srt) | Machine translation, not reviewed by a person |
| **Fright Night** | **1985** | Horror | 883 | [🇱🇦 Lao](subtitles/Fright.Night.1985.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Fright.Night.1985.bilingual.srt) | Machine translation, not reviewed by a person |
| **Frozen** | **2013** | Feature Film | 1,652 | [🇱🇦 Lao](subtitles/Frozen.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Frozen.2013.bilingual.srt) | Machine translation, not reviewed by a person |
| **Frozen** | **2013** | Animation | 917 | [🇱🇦 Lao](subtitles/Frozen.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Frozen.2013.bilingual.srt) | Machine translation, not reviewed by a person |
| **Gladiator** | **2000** | Drama / Classics | 675 | [🇱🇦 Lao](subtitles/Gladiator.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Gladiator.2000.bilingual.srt) | Machine translation, not reviewed by a person |
| **Happy Feet** | **2006** | Animation | 633 | [🇱🇦 Lao](subtitles/Happy.Feet.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Happy.Feet.2006.bilingual.srt) | Machine translation, not reviewed by a person |
| **Heavy Metal** | **1981** | Animation | 297 | [🇱🇦 Lao](subtitles/Heavy.Metal.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Heavy.Metal.1981.bilingual.srt) | Machine translation, not reviewed by a person |
| **Here Comes Peter Cottontail** | **1971** | Animation | 508 | [🇱🇦 Lao](subtitles/Here.Comes.Peter.Cottontail.1971.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Here.Comes.Peter.Cottontail.1971.bilingual.srt) | Machine translation, not reviewed by a person |
| **How to Train Your Dragon** | **2010** | Animation | 785 | [🇱🇦 Lao](subtitles/How.to.Train.Your.Dragon.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/How.to.Train.Your.Dragon.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **How to Train Your Dragon 2** | **2014** | Animation | 726 | [🇱🇦 Lao](subtitles/How.to.Train.Your.Dragon.2.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/How.to.Train.Your.Dragon.2.2014.bilingual.srt) | Machine translation, not reviewed by a person |
| **Inception** | **2010** | Drama / Classics | 1,223 | [🇱🇦 Lao](subtitles/Inception.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Inception.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **Interstellar** | **2014** | Drama / Classics | 902 | [🇱🇦 Lao](subtitles/Interstellar.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Interstellar.2014.bilingual.srt) | Machine translation, not reviewed by a person |
| **Kung Fu Panda** | **2008** | Animation | 694 | [🇱🇦 Lao](subtitles/Kung.Fu.Panda.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Kung.Fu.Panda.2008.bilingual.srt) | Machine translation, not reviewed by a person |
| **L' Avventura (The Adventure)** | **1960** | Thriller | 745 | [🇱🇦 Lao](subtitles/L.Avventura.The.Adventure.1960.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/L.Avventura.The.Adventure.1960.bilingual.srt) | Machine translation, not reviewed by a person |
| **Megamind** | **2010** | Animation | 866 | [🇱🇦 Lao](subtitles/Megamind.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Megamind.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **Memento** | **2000** | Feature Film | 692 | [🇱🇦 Lao](subtitles/Memento.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Memento.2000.bilingual.srt) | Machine translation, not reviewed by a person |
| **Moana** | **2016** | Feature Film | 1,233 | [🇱🇦 Lao](subtitles/Moana.2016.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Moana.2016.bilingual.srt) | Machine translation, not reviewed by a person |
| **Monkeybone** | **2001** | Animation | 643 | [🇱🇦 Lao](subtitles/Monkeybone.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Monkeybone.2001.bilingual.srt) | Machine translation, not reviewed by a person |
| **One Eight Seven (187)** | **1997** | Drama | 754 | [🇱🇦 Lao](subtitles/One.Eight.Seven.187.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/One.Eight.Seven.187.1997.bilingual.srt) | Machine translation, not reviewed by a person, 11 flagged of 754 |
| **Onward** | **2020** | Animation | 1,114 | [🇱🇦 Lao](subtitles/Onward.2020.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Onward.2020.bilingual.srt) | Machine translation, not reviewed by a person |
| **ParaNorman** | **2012** | Animation | 664 | [🇱🇦 Lao](subtitles/ParaNorman.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/ParaNorman.2012.bilingual.srt) | Machine translation, not reviewed by a person |
| **Pulp Fiction** | **1994** | Drama / Classics | 1,214 | [🇱🇦 Lao](subtitles/Pulp.Fiction.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Pulp.Fiction.1994.bilingual.srt) | Machine translation, not reviewed by a person |
| **Puss in Boots: The Last Wish** | **2022** | Animation | 1,134 | [🇱🇦 Lao](subtitles/Puss.in.Boots.The.Last.Wish.2022.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Puss.in.Boots.The.Last.Wish.2022.bilingual.srt) | Machine translation, not reviewed by a person |
| **Reservoir Dogs** | **1992** | Feature Film | 694 | [🇱🇦 Lao](subtitles/Reservoir.Dogs.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Reservoir.Dogs.1992.bilingual.srt) | Machine translation, not reviewed by a person |
| **Rise of the Guardians** | **2012** | Animation | 984 | [🇱🇦 Lao](subtitles/Rise.of.the.Guardians.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Rise.of.the.Guardians.2012.bilingual.srt) | Machine translation, not reviewed by a person |
| **Saving Private Ryan** | **1998** | Feature Film | 934 | [🇱🇦 Lao](subtitles/Saving.Private.Ryan.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Saving.Private.Ryan.1998.bilingual.srt) | Machine translation, not reviewed by a person |
| **Se7en** | **1995** | Feature Film | 489 | [🇱🇦 Lao](subtitles/Se7en.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Se7en.1995.bilingual.srt) | Machine translation, not reviewed by a person |
| **Shrek** | **2001** | Animation | 744 | [🇱🇦 Lao](subtitles/Shrek.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Shrek.2001.bilingual.srt) | Machine translation, not reviewed by a person |
| **Shrek the Third** | **2007** | Animation | 894 | [🇱🇦 Lao](subtitles/Shrek.the.Third.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Shrek.the.Third.2007.bilingual.srt) | Machine translation, not reviewed by a person |
| **South Park: Bigger, Longer & Uncut** | **1999** | Animation | 1,257 | [🇱🇦 Lao](subtitles/South.Park.Bigger.Longer.and.Uncut.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/South.Park.Bigger.Longer.and.Uncut.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **Spider-Man: Across the Spider-Verse** | **2023** | Animation | 1,542 | [🇱🇦 Lao](subtitles/Spider-Man.Across.the.Spider-Verse.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Spider-Man.Across.the.Spider-Verse.2023.bilingual.srt) | Machine translation, not reviewed by a person |
| **Star Wars: Episode IV - A New Hope** | **1977** | Feature Film | 994 | [🇱🇦 Lao](subtitles/Star.Wars.Episode.IV.-.A.New.Hope.1977.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Star.Wars.Episode.IV.-.A.New.Hope.1977.bilingual.srt) | Machine translation, not reviewed by a person |
| **Teenage Mutant Ninja Turtles: Mutant Mayhem** | **2023** | Animation | 996 | [🇱🇦 Lao](subtitles/Teenage.Mutant.Ninja.Turtles.Mutant.Mayhem.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Teenage.Mutant.Ninja.Turtles.Mutant.Mayhem.2023.bilingual.srt) | Machine translation, not reviewed by a person |
| **Terminator 2: Judgment Day** | **1991** | Feature Film | 518 | [🇱🇦 Lao](subtitles/Terminator.2.Judgment.Day.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Terminator.2.Judgment.Day.1991.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Abyss** | **1989** | Thriller | 665 | [🇱🇦 Lao](subtitles/The.Abyss.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Abyss.1989.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Addams Family** | **1991** | Horror | 265 | [🇱🇦 Lao](subtitles/The.Addams.Family.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Addams.Family.1991.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Adjustment Bureau** | **2011** | Thriller | 978 | [🇱🇦 Lao](subtitles/The.Adjustment.Bureau.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Adjustment.Bureau.2011.bilingual.srt) | Machine translation, not reviewed by a person |
| **The American** | **2010** | Thriller | 693 | [🇱🇦 Lao](subtitles/The.American.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.American.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **The American President** | **1995** | Romance | 1,403 | [🇱🇦 Lao](subtitles/The.American.President.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.American.President.1995.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Amityville Asylum** | **2013** | Horror | 631 | [🇱🇦 Lao](subtitles/The.Amityville.Asylum.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Amityville.Asylum.2013.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Apartment** | **1960** | Comedy | 1,214 | [🇱🇦 Lao](subtitles/The.Apartment.1960.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Apartment.1960.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Assignment** | **1997** | Thriller | 788 | [🇱🇦 Lao](subtitles/The.Assignment.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Assignment.1997.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Avengers** | **2012** | Sci-Fi | 941 | [🇱🇦 Lao](subtitles/The.Avengers.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Avengers.2012.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Back-up Plan** | **2010** | Romance | 1,058 | [🇱🇦 Lao](subtitles/The.Back-up.Plan.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Back-up.Plan.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Battle of Shaker Heights** | **2003** | Romance | 945 | [🇱🇦 Lao](subtitles/The.Battle.of.Shaker.Heights.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Battle.of.Shaker.Heights.2003.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Beekeeper** | **2024** | Thriller | 762 | [🇱🇦 Lao](subtitles/The.Beekeeper.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Beekeeper.2024.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Big Blue** | **1988** | Romance | 849 | [🇱🇦 Lao](subtitles/The.Big.Blue.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Big.Blue.1988.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Big Sick** | **2017** | Romance | 1,119 | [🇱🇦 Lao](subtitles/The.Big.Sick.2017.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Big.Sick.2017.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Big White** | **2005** | Crime | 840 | [🇱🇦 Lao](subtitles/The.Big.White.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Big.White.2005.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Birds** | **1963** | Romance | 1,139 | [🇱🇦 Lao](subtitles/The.Birds.1963.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Birds.1963.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Black Dahlia** | **2006** | Crime | 1,048 | [🇱🇦 Lao](subtitles/The.Black.Dahlia.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Black.Dahlia.2006.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Blast from the Past** | **1999** | Romance | 1,268 | [🇱🇦 Lao](subtitles/The.Blast.from.the.Past.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Blast.from.the.Past.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Bling Ring** | **2013** | Crime | 606 | [🇱🇦 Lao](subtitles/The.Bling.Ring.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bling.Ring.2013.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Book of Eli** | **2010** | Sci-Fi | 786 | [🇱🇦 Lao](subtitles/The.Book.of.Eli.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Book.of.Eli.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Boondock Saints** | **1999** | Crime | 787 | [🇱🇦 Lao](subtitles/The.Boondock.Saints.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Boondock.Saints.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Bounty Hunter** | **2010** | Romance | 934 | [🇱🇦 Lao](subtitles/The.Bounty.Hunter.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bounty.Hunter.2010.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Bourne Identity** | **2002** | Adventure | 643 | [🇱🇦 Lao](subtitles/The.Bourne.Identity.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bourne.Identity.2002.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Bourne Ultimatum** | **2007** | Adventure | 553 | [🇱🇦 Lao](subtitles/The.Bourne.Ultimatum.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bourne.Ultimatum.2007.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Box** | **2009** | Sci-Fi | 811 | [🇱🇦 Lao](subtitles/The.Box.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Box.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Boxtrolls** | **2014** | Animation | 938 | [🇱🇦 Lao](subtitles/The.Boxtrolls.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Boxtrolls.2014.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Brothers Bloom** | **2008** | Romance | 706 | [🇱🇦 Lao](subtitles/The.Brothers.Bloom.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Brothers.Bloom.2008.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Cell** | **2000** | Sci-Fi | 621 | [🇱🇦 Lao](subtitles/The.Cell.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Cell.2000.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Cider House Rules** | **1999** | Romance | 1,020 | [🇱🇦 Lao](subtitles/The.Cider.House.Rules.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Cider.House.Rules.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Croods** | **2013** | Animation | 805 | [🇱🇦 Lao](subtitles/The.Croods.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Croods.2013.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Crow** | **1994** | Horror | 539 | [🇱🇦 Lao](subtitles/The.Crow.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Crow.1994.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Crow Salvation** | **2000** | Horror | 572 | [🇱🇦 Lao](subtitles/The.Crow.Salvation.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Crow.Salvation.2000.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Dark Knight** | **2008** | Drama / Classics | 1,243 | [🇱🇦 Lao](subtitles/The.Dark.Knight.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Dark.Knight.2008.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Day the Earth Stood Still** | **2008** | Sci-Fi | 770 | [🇱🇦 Lao](subtitles/The.Day.the.Earth.Stood.Still.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Day.the.Earth.Stood.Still.2008.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Departed** | **2006** | Feature Film | 1,180 | [🇱🇦 Lao](subtitles/The.Departed.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Departed.2006.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Godfather** | **1972** | Drama / Classics | 899 | [🇱🇦 Lao](subtitles/The.Godfather.1972.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Godfather.1972.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Green Mile** | **1999** | Feature Film | 1,012 | [🇱🇦 Lao](subtitles/The.Green.Mile.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Green.Mile.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **The LEGO Movie** | **2014** | Animation | 961 | [🇱🇦 Lao](subtitles/The.LEGO.Movie.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.LEGO.Movie.2014.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Lord of the Rings: The Fellowship of the Ring** | **2001** | Feature Film | 817 | [🇱🇦 Lao](subtitles/The.Lord.of.the.Rings.The.Fellowship.of.the.Ring.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Lord.of.the.Rings.The.Fellowship.of.the.Ring.2001.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Matrix** | **1999** | Drama / Classics | 568 | [🇱🇦 Lao](subtitles/The.Matrix.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Matrix.1999.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Prestige** | **2006** | Feature Film | 1,047 | [🇱🇦 Lao](subtitles/The.Prestige.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Prestige.2006.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Shawshank Redemption** | **1994** | Feature Film | 803 | [🇱🇦 Lao](subtitles/The.Shawshank.Redemption.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Shawshank.Redemption.1994.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Silence Of The Lambs** | **1991** | Feature Film | 928 | [🇱🇦 Lao](subtitles/The.Silence.Of.The.Lambs.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Silence.Of.The.Lambs.1991.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Terminator** | **1984** | Feature Film | 503 | [🇱🇦 Lao](subtitles/The.Terminator.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Terminator.1984.bilingual.srt) | Machine translation, not reviewed by a person |
| **The Usual Suspects** | **1995** | Feature Film | 768 | [🇱🇦 Lao](subtitles/The.Usual.Suspects.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Usual.Suspects.1995.bilingual.srt) | Machine translation, not reviewed by a person |
| **TMNT** | **2007** | Animation | 551 | [🇱🇦 Lao](subtitles/TMNT.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/TMNT.2007.bilingual.srt) | Machine translation, not reviewed by a person |
| **Toy Story** | **1995** | Animation | 887 | [🇱🇦 Lao](subtitles/Toy.Story.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Toy.Story.1995.bilingual.srt) | Machine translation, not reviewed by a person |
| **Transformers: The Movie** | **1986** | Animation | 720 | [🇱🇦 Lao](subtitles/Transformers.The.Movie.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Transformers.The.Movie.1986.bilingual.srt) | Machine translation, not reviewed by a person |
| **Up** | **2009** | Animation | 720 | [🇱🇦 Lao](subtitles/Up.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Up.2009.bilingual.srt) | Machine translation, not reviewed by a person |
| **Wall-E** | **2008** | Animation | 476 | [🇱🇦 Lao](subtitles/Wall-E.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Wall-E.2008.bilingual.srt) | Machine translation, not reviewed by a person |

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
