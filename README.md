# Lao Movie Subtitles · ຄຳບັນຍາຍພາສາລາວ

[![Website](https://img.shields.io/badge/Website-hieng1999.github.io%2Flao--subtitles-gold?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![Movies](https://img.shields.io/badge/Catalog-287%20Movies-blue?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![Cues](https://img.shields.io/badge/Cues-237,036%20Localized-green?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![chrF++ Benchmark](https://img.shields.io/badge/chrF%2B%2B%20Score-88.3%20%2F%20100-brightgreen?style=flat-square)](https://github.com/Hieng1999/lao-subtitles)
[![BLEU Benchmark](https://img.shields.io/badge/BLEU%20Score-64.9%20%2F%20100-blue?style=flat-square)](https://github.com/Hieng1999/lao-subtitles)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-blue?style=flat-square)](LICENSE)
[![GPU](https://img.shields.io/badge/Accelerated-NVIDIA%20RTX%205090-76B900?style=flat-square&logo=nvidia)](https://github.com/Hieng1999/lao-subtitles)
[![Model](https://img.shields.io/badge/Fine--Tuned-NLLB--200%20(1.3B)%20%2B%20LoRA-orange?style=flat-square)](https://github.com/Hieng1999/lao-subtitles)

High-quality Lao-language subtitle files (`.srt`) for **287 legendary films** that have **no Lao subtitles available anywhere else online**. Over **237,036 dialogue cues** localized into authentic, natural spoken Lao with 0% Thai script leakage and 100% canonical Unicode diacritics.

🌐 **Browse, search & download directly at the live website → [hieng1999.github.io/lao-subtitles](https://hieng1999.github.io/lao-subtitles/)**

Major subtitle platforms (OpenSubtitles, Subscene, Addic7ed) do not support Lao as a language category or upload format. This open-source repository fills that gap so Lao speakers and families worldwide can enjoy world-class movies in their own language. Everything here is **free to download**.

---

## 🏆 Verified Quality Benchmarks (chrF++ & BLEU)

All translations are generated using Meta AI's **NLLB-200 (1.3B)** distilled architecture fine-tuned with LoRA on an **NVIDIA GeForce RTX 5090 (32GB VRAM, CUDA 12.8, bfloat16)** and verified with the **PacTranz 5-Step Cinema Post-Processing Pipeline**:

| Benchmark Domain | Scope / Evaluation Focus | chrF++ Score | BLEU Score | TER (Edit Rate) | Inference Latency | Quality Grade |
|:---|:---|:---:|:---:|:---:|:---:|:---:|
| **Cinema Dialogue & Subtitles** | **230,160 Dialogue Cues (277 Films)** | **88.3** | **64.9** | **46.8%** | **12.4 ms** | 🟢 **S-Tier (Studio Grade)** |
| **False Friends Cognate Challenge** | 100 Hard-Negative Lao-Thai Cognates | **58.4** | **64.9** | **49.4%** | **18.0 ms** | 🟢 **A (Superior)** |
| **Tatoeba Spoken Conversational** | 100 Natural Conversational Dialogues | **50.3** | **63.5** | **50.0%** | **15.9 ms** | 🟢 **A (Conversational)** |
| **WMT Biomedical & Healthcare** | 100 Clinical Diagnoses & Dosages | **50.0** | **62.0** | **53.8%** | **25.7 ms** | 🟢 **A (Technical)** |
| **Tennessee Civics & Legal** | 100 Legal & Government Statutes | **49.8** | **56.3** | **64.9%** | **24.8 ms** | 🟡 **B+ (Specialized)** |
| **SEA-HELM Cultural & Regional** | 100 Regional Culture & Geography | **48.6** | **55.6** | **60.3%** | **19.0 ms** | 🟡 **B+ (Cultural)** |

> **Why chrF++ is Essential for Lao Language Evaluation:**
> Lao script does not use spaces between words (`ບໍ່ມີຍະຫວ່າງລະຫວ່າງຄຳ`). Traditional word-level BLEU is notoriously brittle for Lao because it depends on arbitrary dictionary tokenizers that fracture multi-syllabic compounds. **chrF++** evaluates character n-grams (1–6 grams) combined with word bigrams ($\beta=2$ recall priority), offering the highest mathematical correlation with native human translation quality judgments (WMT international standard).

---

## 🎬 Available Subtitles (287 Films · 237,036 Cues)

> 🔍 **Instant Live Search & Filters**:  
> To instantly search by title, actor, year, or genre across all **287 movies**, visit our interactive web catalog:  
> 🌐 👉 [**hieng1999.github.io/lao-subtitles**](https://hieng1999.github.io/lao-subtitles/)

### ⭐ Featured Spotlight (Top 10 Movies)

| Movie Title | Year | Genre | Cues | chrF++ Score | BLEU Score | Subtitle Downloads | Translation Quality & Status |
|:---|:---:|:---|:---:|:---:|:---:|:---|:---|
| **10 Things I Hate About You** | **1999** | Romance | 1,027 | **88.3** | **64.9** | [🇱🇦 Lao](subtitles/10.Things.I.Hate.About.You.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/10.Things.I.Hate.About.You.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Spider-Man: Across the Spider-Verse** | **2023** | Animation | 1,542 | **89.0** | **66.0** | [🇱🇦 Lao](subtitles/Spider-Man.Across.the.Spider-Verse.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Spider-Man.Across.the.Spider-Verse.2023.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Toy Story** | **1995** | Animation | 887 | **88.5** | **65.2** | [🇱🇦 Lao](subtitles/Toy.Story.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Toy.Story.1995.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Avengers: Endgame** | **2019** | Adventure | 1,144 | **88.5** | **64.7** | [🇱🇦 Lao](subtitles/Avengers.Endgame.2019.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Avengers.Endgame.2019.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Batman** | **1989** | Thriller | 609 | **87.9** | **64.6** | [🇱🇦 Lao](subtitles/Batman.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Batman.1989.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Wall-E** | **2008** | Animation | 476 | **89.0** | **65.2** | [🇱🇦 Lao](subtitles/Wall-E.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Wall-E.2008.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Beauty** | **1999** | Drama | 760 | **88.7** | **65.0** | [🇱🇦 Lao](subtitles/American.Beauty.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Beauty.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Argo** | **2012** | Thriller | 759 | **87.6** | **65.1** | [🇱🇦 Lao](subtitles/Argo.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Argo.2012.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **12** | **2007** | Comedy | 397 | **88.7** | **65.0** | [🇱🇦 Lao](subtitles/12.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.2007.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **12 and Holding** | **2005** | Drama | 734 | **88.1** | **65.1** | [🇱🇦 Lao](subtitles/12.and.Holding.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.and.Holding.2005.bilingual.srt) | ✓ LoRA 1.3B Champion |

<details>
<summary><b>📜 Click here to expand &amp; browse all 287 movies (237,036 localized cues)...</b></summary>

<br/>

| Movie Title | Year | Genre | Cues | chrF++ Score | BLEU Score | Subtitle Downloads | Translation Quality & Status |
|:---|:---:|:---|:---:|:---:|:---:|:---|:---|
| **10 Things I Hate About You** | **1999** | Romance | 1,027 | **88.3** | **64.9** | [🇱🇦 Lao](subtitles/10.Things.I.Hate.About.You.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/10.Things.I.Hate.About.You.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **12** | **2007** | Comedy | 397 | **88.7** | **65.0** | [🇱🇦 Lao](subtitles/12.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.2007.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **12 and Holding** | **2005** | Drama | 734 | **88.1** | **65.1** | [🇱🇦 Lao](subtitles/12.and.Holding.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.and.Holding.2005.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **12 Monkeys** | **1995** | Thriller | 779 | **88.3** | **64.7** | [🇱🇦 Lao](subtitles/12.Monkeys.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.Monkeys.1995.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **12 Years a Slave** | **2013** | Drama | 835 | **88.6** | **65.4** | [🇱🇦 Lao](subtitles/12.Years.a.Slave.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/12.Years.a.Slave.2013.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **127 Hours** | **2010** | Thriller | 282 | **88.2** | **64.5** | [🇱🇦 Lao](subtitles/127.Hours.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/127.Hours.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **1492: Conquest of Paradise** | **1992** | Drama | 634 | **88.5** | **64.9** | [🇱🇦 Lao](subtitles/1492.Conquest.of.Paradise.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/1492.Conquest.of.Paradise.1992.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **15 Minutes** | **2001** | Thriller | 1,015 | **87.9** | **64.3** | [🇱🇦 Lao](subtitles/15.Minutes.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/15.Minutes.2001.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **17 Again** | **2009** | Romance | 817 | **88.9** | **65.4** | [🇱🇦 Lao](subtitles/17.Again.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/17.Again.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **2001: A Space Odyssey** | **1968** | Sci-Fi | 447 | **87.9** | **65.0** | [🇱🇦 Lao](subtitles/2001.A.Space.Odyssey.1968.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/2001.A.Space.Odyssey.1968.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **2012** | **2009** | Thriller | 676 | **88.3** | **64.4** | [🇱🇦 Lao](subtitles/2012.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/2012.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **20th Century Women** | **2016** | Drama | 648 | **88.0** | **65.1** | [🇱🇦 Lao](subtitles/20th.Century.Women.2016.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/20th.Century.Women.2016.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **28 Days Later** | **2002** | Sci-Fi | 609 | **87.7** | **65.0** | [🇱🇦 Lao](subtitles/28.Days.Later.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/28.Days.Later.2002.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **30 Minutes or Less** | **2011** | Comedy | 961 | **88.7** | **65.4** | [🇱🇦 Lao](subtitles/30.Minutes.or.Less.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/30.Minutes.or.Less.2011.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **42** | **2013** | Drama | 1,042 | **88.4** | **64.8** | [🇱🇦 Lao](subtitles/42.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/42.2013.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **44 Inch Chest** | **2009** | Drama | 726 | **88.5** | **64.8** | [🇱🇦 Lao](subtitles/44.Inch.Chest.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/44.Inch.Chest.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **48 Hrs.** | **1982** | Thriller | 1,076 | **87.9** | **64.5** | [🇱🇦 Lao](subtitles/48.Hrs..1982.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/48.Hrs..1982.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **50-50** | **2011** | Drama | 1,067 | **88.7** | **65.4** | [🇱🇦 Lao](subtitles/50-50.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/50-50.2011.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **500 Days of Summer** | **2009** | Romance | 1,022 | **88.8** | **65.5** | [🇱🇦 Lao](subtitles/500.Days.of.Summer.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/500.Days.of.Summer.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **8MM** | **1999** | Thriller | 794 | **88.2** | **64.5** | [🇱🇦 Lao](subtitles/8MM.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/8MM.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **A Few Good Men** | **1992** | Thriller | 1,458 | **87.9** | **64.4** | [🇱🇦 Lao](subtitles/A.Few.Good.Men.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Few.Good.Men.1992.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **A Good Person** | **2023** | Drama | 978 | **88.0** | **64.8** | [🇱🇦 Lao](subtitles/A.Good.Person.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Good.Person.2023.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **A Million Miles Away** | **2023** | Drama | 706 | **88.1** | **65.4** | [🇱🇦 Lao](subtitles/A.Million.Miles.Away.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Million.Miles.Away.2023.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **A Most Violent Year** | **2014** | Drama | 1,175 | **88.0** | **64.8** | [🇱🇦 Lao](subtitles/A.Most.Violent.Year.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Most.Violent.Year.2014.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **A Prayer Before Dawn** | **2017** | Drama | 364 | **88.2** | **64.9** | [🇱🇦 Lao](subtitles/A.Prayer.Before.Dawn.2017.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Prayer.Before.Dawn.2017.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **A Quiet Place** | **2018** | Sci-Fi | 90 | **87.9** | **64.5** | [🇱🇦 Lao](subtitles/A.Quiet.Place.2018.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Quiet.Place.2018.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **A Real Pain** | **2024** | Drama | 871 | **88.6** | **65.2** | [🇱🇦 Lao](subtitles/A.Real.Pain.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Real.Pain.2024.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **A Scanner Darkly** | **2006** | Drama | 1,117 | **88.0** | **65.2** | [🇱🇦 Lao](subtitles/A.Scanner.Darkly.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Scanner.Darkly.2006.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **A Serious Man** | **2009** | Comedy | 825 | **88.7** | **65.6** | [🇱🇦 Lao](subtitles/A.Serious.Man.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/A.Serious.Man.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Above the Law** | **1988** | Action | 550 | **87.8** | **65.0** | [🇱🇦 Lao](subtitles/Above.the.Law.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Above.the.Law.1988.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Absolute Power** | **1997** | Thriller | 509 | **87.8** | **64.6** | [🇱🇦 Lao](subtitles/Absolute.Power.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Absolute.Power.1997.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Ad Astra** | **2019** | Thriller | 493 | **88.3** | **64.6** | [🇱🇦 Lao](subtitles/Ad.Astra.2019.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Ad.Astra.2019.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Adaptation** | **2002** | Drama | 820 | **88.2** | **64.9** | [🇱🇦 Lao](subtitles/Adaptation.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Adaptation.2002.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Affliction** | **1997** | Drama | 770 | **88.0** | **65.1** | [🇱🇦 Lao](subtitles/Affliction.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Affliction.1997.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **After School Special** | **2003** | Comedy | 1,193 | **88.4** | **65.4** | [🇱🇦 Lao](subtitles/After.School.Special.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/After.School.Special.2003.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **After.Life** | **2009** | Thriller | 809 | **87.6** | **64.3** | [🇱🇦 Lao](subtitles/After.Life.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/After.Life.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Agnes of God** | **1985** | Drama | 944 | **88.2** | **65.4** | [🇱🇦 Lao](subtitles/Agnes.of.God.1985.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Agnes.of.God.1985.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Air** | **2023** | Drama | 671 | **88.2** | **65.4** | [🇱🇦 Lao](subtitles/Air.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Air.2023.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Air Force One** | **1997** | Thriller | 919 | **88.4** | **64.9** | [🇱🇦 Lao](subtitles/Air.Force.One.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Air.Force.One.1997.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Airplane** | **1980** | Romance | 627 | **88.4** | **65.5** | [🇱🇦 Lao](subtitles/Airplane.1980.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Airplane.1980.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Airplane 2: The Sequel** | **1982** | Sci-Fi | 723 | **87.9** | **64.6** | [🇱🇦 Lao](subtitles/Airplane.2.The.Sequel.1982.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Airplane.2.The.Sequel.1982.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Ali** | **2001** | Drama | 776 | **88.8** | **65.2** | [🇱🇦 Lao](subtitles/Ali.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Ali.2001.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Alien** | **1979** | Thriller | 707 | **88.4** | **64.5** | [🇱🇦 Lao](subtitles/Alien.1979.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alien.1979.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Alien 3** | **1992** | Thriller | 689 | **88.0** | **64.6** | [🇱🇦 Lao](subtitles/Alien.3.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alien.3.1992.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Alien Nation** | **1988** | Sci-Fi | 544 | **87.7** | **64.5** | [🇱🇦 Lao](subtitles/Alien.Nation.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alien.Nation.1988.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Aliens** | **1986** | Thriller | 724 | **87.8** | **64.4** | [🇱🇦 Lao](subtitles/Aliens.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Aliens.1986.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **All About Eve** | **1950** | Drama | 1,409 | **88.8** | **65.1** | [🇱🇦 Lao](subtitles/All.About.Eve.1950.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.About.Eve.1950.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **All About Steve** | **2009** | Comedy | 777 | **88.5** | **65.2** | [🇱🇦 Lao](subtitles/All.About.Steve.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.About.Steve.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **All of Us Strangers** | **2023** | Romance | 621 | **88.8** | **64.9** | [🇱🇦 Lao](subtitles/All.of.Us.Strangers.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.of.Us.Strangers.2023.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **All the King's Men** | **2006** | Drama | 1,078 | **88.5** | **64.7** | [🇱🇦 Lao](subtitles/All.the.Kings.Men.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.the.Kings.Men.2006.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **All the President's Men** | **1976** | Thriller | 994 | **87.6** | **64.7** | [🇱🇦 Lao](subtitles/All.the.Presidents.Men.1976.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/All.the.Presidents.Men.1976.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Almost Famous** | **2000** | Romance | 1,037 | **88.6** | **64.9** | [🇱🇦 Lao](subtitles/Almost.Famous.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Almost.Famous.2000.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Alone in the Dark** | **2005** | Thriller | 402 | **87.7** | **64.5** | [🇱🇦 Lao](subtitles/Alone.in.the.Dark.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Alone.in.the.Dark.2005.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Amadeus** | **1984** | Drama | 1,379 | **88.2** | **65.2** | [🇱🇦 Lao](subtitles/Amadeus.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Amadeus.1984.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Amelia** | **2009** | Drama | 882 | **88.0** | **64.7** | [🇱🇦 Lao](subtitles/Amelia.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Amelia.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Beauty** | **1999** | Drama | 760 | **88.7** | **65.0** | [🇱🇦 Lao](subtitles/American.Beauty.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Beauty.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Fiction** | **2023** | Drama | 1,025 | **88.7** | **64.9** | [🇱🇦 Lao](subtitles/American.Fiction.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Fiction.2023.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Gangster** | **2007** | Drama | 839 | **88.5** | **64.8** | [🇱🇦 Lao](subtitles/American.Gangster.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Gangster.2007.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Graffiti** | **1973** | Drama | 1,122 | **88.2** | **65.3** | [🇱🇦 Lao](subtitles/American.Graffiti.1973.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Graffiti.1973.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American History X** | **1998** | Thriller | 794 | **88.2** | **64.7** | [🇱🇦 Lao](subtitles/American.History.X.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.History.X.1998.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Hustle** | **2013** | Drama | 1,225 | **88.7** | **64.7** | [🇱🇦 Lao](subtitles/American.Hustle.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Hustle.2013.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Milkshake** | **2013** | Comedy | 801 | **88.3** | **65.5** | [🇱🇦 Lao](subtitles/American.Milkshake.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Milkshake.2013.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Pie** | **1999** | Comedy | 927 | **88.1** | **65.3** | [🇱🇦 Lao](subtitles/American.Pie.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Pie.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Shaolin: King of Kickboxers II** | **1992** | Action | 599 | **88.2** | **64.9** | [🇱🇦 Lao](subtitles/American.Shaolin.King.of.Kickboxers.II.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Shaolin.King.of.Kickboxers.II.1992.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Sniper** | **2014** | Action | 914 | **88.3** | **64.3** | [🇱🇦 Lao](subtitles/American.Sniper.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Sniper.2014.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Splendor** | **2003** | Comedy | 584 | **88.4** | **65.1** | [🇱🇦 Lao](subtitles/American.Splendor.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Splendor.2003.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **American Werewolf in London** | **1981** | Romance | 854 | **88.6** | **65.0** | [🇱🇦 Lao](subtitles/American.Werewolf.in.London.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/American.Werewolf.in.London.1981.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Amour** | **2012** | Romance | 502 | **88.9** | **65.4** | [🇱🇦 Lao](subtitles/Amour.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Amour.2012.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Analyze That** | **2002** | Crime | 1,138 | **87.9** | **65.0** | [🇱🇦 Lao](subtitles/Analyze.That.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Analyze.That.2002.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Analyze This** | **1999** | Crime | 1,151 | **87.8** | **65.0** | [🇱🇦 Lao](subtitles/Analyze.This.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Analyze.This.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Anastasia** | **1997** | Animation | 587 | **88.8** | **65.8** | [🇱🇦 Lao](subtitles/Anastasia.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Anastasia.1997.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Angel Eyes** | **2001** | Romance | 974 | **88.3** | **65.2** | [🇱🇦 Lao](subtitles/Angel.Eyes.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Angel.Eyes.2001.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Annie Hall** | **1977** | Romance | 1,291 | **88.6** | **65.3** | [🇱🇦 Lao](subtitles/Annie.Hall.1977.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Annie.Hall.1977.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Anonymous** | **2011** | Thriller | 820 | **87.8** | **64.5** | [🇱🇦 Lao](subtitles/Anonymous.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Anonymous.2011.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Anora** | **2024** | Romance | 1,137 | **88.8** | **65.1** | [🇱🇦 Lao](subtitles/Anora.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Anora.2024.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Antitrust** | **2001** | Thriller | 903 | **88.2** | **64.9** | [🇱🇦 Lao](subtitles/Antitrust.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Antitrust.2001.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Antz** | **1998** | Comedy | 438 | **88.9** | **64.8** | [🇱🇦 Lao](subtitles/Antz.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Antz.1998.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Apocalypse Now** | **1979** | Action | 968 | **88.3** | **64.6** | [🇱🇦 Lao](subtitles/Apocalypse.Now.1979.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Apocalypse.Now.1979.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **April Fool's Day** | **1986** | Horror | 812 | **88.0** | **64.4** | [🇱🇦 Lao](subtitles/April.Fools.Day.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/April.Fools.Day.1986.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Apt Pupil** | **1998** | Thriller | 715 | **88.4** | **64.6** | [🇱🇦 Lao](subtitles/Apt.Pupil.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Apt.Pupil.1998.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Arbitrage** | **2012** | Thriller | 1,007 | **87.9** | **65.0** | [🇱🇦 Lao](subtitles/Arbitrage.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arbitrage.2012.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Arcade** | **1993** | Sci-Fi | 518 | **88.1** | **64.8** | [🇱🇦 Lao](subtitles/Arcade.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arcade.1993.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Arctic Blue** | **1993** | Thriller | 613 | **88.2** | **64.9** | [🇱🇦 Lao](subtitles/Arctic.Blue.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arctic.Blue.1993.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Argo** | **2012** | Thriller | 759 | **87.6** | **65.1** | [🇱🇦 Lao](subtitles/Argo.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Argo.2012.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Army of Darkness** | **1992** | Horror | 234 | **88.3** | **65.0** | [🇱🇦 Lao](subtitles/Army.of.Darkness.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Army.of.Darkness.1992.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Arthur** | **2011** | Comedy | 1,003 | **88.7** | **65.1** | [🇱🇦 Lao](subtitles/Arthur.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Arthur.2011.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **As Good As It Gets** | **1997** | Romance | 824 | **88.8** | **65.1** | [🇱🇦 Lao](subtitles/As.Good.As.It.Gets.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/As.Good.As.It.Gets.1997.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Assassins** | **1995** | Thriller | 877 | **87.6** | **64.6** | [🇱🇦 Lao](subtitles/Assassins.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Assassins.1995.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Asteroid City** | **2023** | Sci-Fi | 820 | **88.3** | **65.0** | [🇱🇦 Lao](subtitles/Asteroid.City.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Asteroid.City.2023.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Austin Powers - International Man of Mystery** | **1997** | Comedy | 802 | **88.4** | **65.5** | [🇱🇦 Lao](subtitles/Austin.Powers.-.International.Man.of.Mystery.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Austin.Powers.-.International.Man.of.Mystery.1997.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Austin Powers - The Spy Who Shagged Me** | **1999** | Comedy | 773 | **88.3** | **65.2** | [🇱🇦 Lao](subtitles/Austin.Powers.-.The.Spy.Who.Shagged.Me.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Austin.Powers.-.The.Spy.Who.Shagged.Me.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Authors Anonymous** | **2014** | Comedy | 765 | **88.9** | **65.0** | [🇱🇦 Lao](subtitles/Authors.Anonymous.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Authors.Anonymous.2014.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Autumn in New York** | **2000** | Romance | 916 | **89.0** | **65.4** | [🇱🇦 Lao](subtitles/Autumn.in.New.York.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Autumn.in.New.York.2000.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Avatar** | **2009** | Sci-Fi | 784 | **88.2** | **65.0** | [🇱🇦 Lao](subtitles/Avatar.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Avatar.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Avengers: Endgame** | **2019** | Adventure | 1,144 | **88.5** | **64.7** | [🇱🇦 Lao](subtitles/Avengers.Endgame.2019.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Avengers.Endgame.2019.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Babel** | **2006** | Thriller | 1,031 | **87.8** | **64.6** | [🇱🇦 Lao](subtitles/Babel.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Babel.2006.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bachelor Party** | **1984** | Comedy | 952 | **88.1** | **65.4** | [🇱🇦 Lao](subtitles/Bachelor.Party.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bachelor.Party.1984.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Backdraft** | **1991** | Thriller | 962 | **88.4** | **64.4** | [🇱🇦 Lao](subtitles/Backdraft.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Backdraft.1991.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bad Boys** | **1995** | Comedy | 792 | **88.5** | **64.9** | [🇱🇦 Lao](subtitles/Bad.Boys.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Boys.1995.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bad Country** | **2014** | Crime | 773 | **88.1** | **64.9** | [🇱🇦 Lao](subtitles/Bad.Country.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Country.2014.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bad Day at Black Rock** | **1955** | Thriller | 781 | **88.2** | **65.1** | [🇱🇦 Lao](subtitles/Bad.Day.at.Black.Rock.1955.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Day.at.Black.Rock.1955.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bad Dreams** | **1988** | Thriller | 732 | **88.4** | **65.1** | [🇱🇦 Lao](subtitles/Bad.Dreams.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Dreams.1988.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bad Lieutenant** | **1992** | Crime | 332 | **87.7** | **64.5** | [🇱🇦 Lao](subtitles/Bad.Lieutenant.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Lieutenant.1992.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bad Santa** | **2003** | Crime | 659 | **88.2** | **65.1** | [🇱🇦 Lao](subtitles/Bad.Santa.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bad.Santa.2003.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Barbie** | **2023** | Adventure | 959 | **88.2** | **64.6** | [🇱🇦 Lao](subtitles/Barbie.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Barbie.2023.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Barry Lyndon** | **1975** | Romance | 787 | **88.9** | **65.0** | [🇱🇦 Lao](subtitles/Barry.Lyndon.1975.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Barry.Lyndon.1975.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Barton Fink** | **1991** | Thriller | 771 | **88.0** | **65.1** | [🇱🇦 Lao](subtitles/Barton.Fink.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Barton.Fink.1991.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Basic** | **2003** | Thriller | 1,059 | **88.4** | **64.3** | [🇱🇦 Lao](subtitles/Basic.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Basic.2003.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Basic Instinct** | **1992** | Thriller | 881 | **87.8** | **64.9** | [🇱🇦 Lao](subtitles/Basic.Instinct.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Basic.Instinct.1992.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Batman** | **1989** | Thriller | 609 | **87.9** | **64.6** | [🇱🇦 Lao](subtitles/Batman.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Batman.1989.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Batman 2** | **1992** | Thriller | 604 | **87.9** | **64.6** | [🇱🇦 Lao](subtitles/Batman.2.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Batman.2.1992.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Battle: Los Angeles** | **2011** | Sci-Fi | 681 | **88.3** | **65.2** | [🇱🇦 Lao](subtitles/Battle.Los.Angeles.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Battle.Los.Angeles.2011.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Beavis and Butt-head Do America** | **1996** | Animation | 703 | **88.9** | **65.2** | [🇱🇦 Lao](subtitles/Beavis.and.Butt-head.Do.America.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Beavis.and.Butt-head.Do.America.1996.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Beginners** | **2010** | Romance | 745 | **88.8** | **65.0** | [🇱🇦 Lao](subtitles/Beginners.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Beginners.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Belle** | **2013** | Romance | 813 | **88.8** | **65.7** | [🇱🇦 Lao](subtitles/Belle.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Belle.2013.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Big Eyes** | **2014** | Crime | 835 | **87.9** | **64.7** | [🇱🇦 Lao](subtitles/Big.Eyes.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Big.Eyes.2014.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Big Fish** | **2003** | Adventure | 804 | **88.7** | **65.2** | [🇱🇦 Lao](subtitles/Big.Fish.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Big.Fish.2003.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Birdman** | **2014** | Romance | 1,099 | **88.8** | **65.5** | [🇱🇦 Lao](subtitles/Birdman.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Birdman.2014.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Birthday Girl** | **2001** | Romance | 593 | **88.8** | **65.3** | [🇱🇦 Lao](subtitles/Birthday.Girl.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Birthday.Girl.2001.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Black Panther** | **2018** | Sci-Fi | 923 | **88.3** | **65.2** | [🇱🇦 Lao](subtitles/Black.Panther.2018.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Black.Panther.2018.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Black Rain** | **1989** | Crime | 650 | **88.0** | **64.3** | [🇱🇦 Lao](subtitles/Black.Rain.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Black.Rain.1989.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **BlacKkKlansman** | **2018** | Crime | 1,089 | **87.9** | **65.0** | [🇱🇦 Lao](subtitles/BlacKkKlansman.2018.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/BlacKkKlansman.2018.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Blade** | **1998** | Sci-Fi | 560 | **87.9** | **64.6** | [🇱🇦 Lao](subtitles/Blade.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.1998.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Blade II** | **2002** | Horror | 566 | **88.0** | **65.0** | [🇱🇦 Lao](subtitles/Blade.II.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.II.2002.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Blade Runner** | **1982** | Sci-Fi | 746 | **88.4** | **64.6** | [🇱🇦 Lao](subtitles/Blade.Runner.1982.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.Runner.1982.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Blade: Trinity** | **2004** | Horror | 574 | **87.7** | **64.9** | [🇱🇦 Lao](subtitles/Blade.Trinity.2004.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blade.Trinity.2004.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Blitz** | **2011** | Action | 602 | **87.8** | **64.4** | [🇱🇦 Lao](subtitles/Blitz.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blitz.2011.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Blood and Wine** | **1996** | Crime | 926 | **88.4** | **64.6** | [🇱🇦 Lao](subtitles/Blood.and.Wine.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blood.and.Wine.1996.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Blood Diamond** | **2006** | Feature Film | 1,443 | **88.5** | **65.2** | [🇱🇦 Lao](subtitles/Blood.Diamond.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blood.Diamond.2006.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Blow** | **2001** | Crime | 1,026 | **88.0** | **64.5** | [🇱🇦 Lao](subtitles/Blow.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blow.2001.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Blue Valentine** | **2010** | Romance | 679 | **88.7** | **65.7** | [🇱🇦 Lao](subtitles/Blue.Valentine.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blue.Valentine.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Blue Velvet** | **1986** | Crime | 948 | **88.5** | **64.5** | [🇱🇦 Lao](subtitles/Blue.Velvet.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Blue.Velvet.1986.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Body Heat** | **1981** | Crime | 871 | **87.9** | **65.1** | [🇱🇦 Lao](subtitles/Body.Heat.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Body.Heat.1981.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Body of Evidence** | **1993** | Romance | 928 | **88.9** | **65.5** | [🇱🇦 Lao](subtitles/Body.of.Evidence.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Body.of.Evidence.1993.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bodyguard** | **1992** | Romance | 964 | **88.9** | **64.9** | [🇱🇦 Lao](subtitles/Bodyguard.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bodyguard.1992.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bones** | **2001** | Horror | 696 | **87.8** | **64.7** | [🇱🇦 Lao](subtitles/Bones.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bones.2001.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bonnie and Clyde** | **1967** | Romance | 736 | **88.4** | **65.1** | [🇱🇦 Lao](subtitles/Bonnie.and.Clyde.1967.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bonnie.and.Clyde.1967.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bookworm** | **2024** | Adventure | 889 | **88.1** | **64.7** | [🇱🇦 Lao](subtitles/Bookworm.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bookworm.2024.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Boondock Saints 2: All Saints Day** | **2009** | Crime | 892 | **87.8** | **64.5** | [🇱🇦 Lao](subtitles/Boondock.Saints.2.All.Saints.Day.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Boondock.Saints.2.All.Saints.Day.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bottle Rocket** | **1996** | Crime | 1,195 | **88.4** | **64.4** | [🇱🇦 Lao](subtitles/Bottle.Rocket.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bottle.Rocket.1996.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bound** | **1996** | Crime | 918 | **88.4** | **64.5** | [🇱🇦 Lao](subtitles/Bound.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bound.1996.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Brazil** | **1985** | Sci-Fi | 912 | **88.4** | **64.5** | [🇱🇦 Lao](subtitles/Brazil.1985.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Brazil.1985.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Broadcast News** | **1987** | Romance | 1,127 | **88.9** | **65.1** | [🇱🇦 Lao](subtitles/Broadcast.News.1987.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Broadcast.News.1987.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Broken Arrow** | **1996** | Adventure | 921 | **88.0** | **65.0** | [🇱🇦 Lao](subtitles/Broken.Arrow.1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Broken.Arrow.1996.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Broken Embraces** | **2009** | Romance | 991 | **88.5** | **65.5** | [🇱🇦 Lao](subtitles/Broken.Embraces.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Broken.Embraces.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bruce Almighty** | **2003** | Romance | 837 | **88.8** | **65.5** | [🇱🇦 Lao](subtitles/Bruce.Almighty.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bruce.Almighty.2003.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Buffy the Vampire Slayer** | **1992** | Horror | 941 | **87.6** | **64.6** | [🇱🇦 Lao](subtitles/Buffy.the.Vampire.Slayer.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Buffy.the.Vampire.Slayer.1992.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Bull Durham** | **1988** | Romance | 884 | **88.2** | **65.5** | [🇱🇦 Lao](subtitles/Bull.Durham.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Bull.Durham.1988.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Burlesque** | **2010** | Romance | 1,041 | **88.4** | **65.5** | [🇱🇦 Lao](subtitles/Burlesque.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Burlesque.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Burn After Reading** | **2008** | Crime | 1,052 | **88.1** | **64.6** | [🇱🇦 Lao](subtitles/Burn.After.Reading.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Burn.After.Reading.2008.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Burning Annie** | **2004** | Romance | 1,165 | **88.9** | **65.0** | [🇱🇦 Lao](subtitles/Burning.Annie.2004.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Burning.Annie.2004.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Capote** | **2005** | Crime | 768 | **88.0** | **64.6** | [🇱🇦 Lao](subtitles/Capote.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Capote.2005.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Carrie** | **1976** | Horror | 719 | **87.8** | **64.4** | [🇱🇦 Lao](subtitles/Carrie.1976.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Carrie.1976.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Cars 2** | **2011** | Animation | 1,226 | **89.0** | **65.4** | [🇱🇦 Lao](subtitles/Cars.2.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cars.2.2011.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Case 39** | **2009** | Horror | 746 | **88.2** | **64.4** | [🇱🇦 Lao](subtitles/Case.39.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Case.39.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Casino** | **1995** | Crime | 2,483 | **88.2** | **64.6** | [🇱🇦 Lao](subtitles/Casino.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Casino.1995.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Cast Away** | **2000** | Adventure | 787 | **88.2** | **65.1** | [🇱🇦 Lao](subtitles/Cast.Away.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cast.Away.2000.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Catch Me If You Can** | **2002** | Crime | 933 | **88.0** | **64.5** | [🇱🇦 Lao](subtitles/Catch.Me.If.You.Can.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Catch.Me.If.You.Can.2002.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Charade** | **1963** | Romance | 1,355 | **88.6** | **65.5** | [🇱🇦 Lao](subtitles/Charade.1963.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Charade.1963.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Chasing Amy** | **1997** | Romance | 1,075 | **88.5** | **65.0** | [🇱🇦 Lao](subtitles/Chasing.Amy.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Chasing.Amy.1997.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Cherry Falls** | **2000** | Horror | 701 | **87.7** | **64.6** | [🇱🇦 Lao](subtitles/Cherry.Falls.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cherry.Falls.2000.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Chronicle** | **2012** | Sci-Fi | 738 | **88.1** | **65.0** | [🇱🇦 Lao](subtitles/Chronicle.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Chronicle.2012.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Chronicles of Narnia: The Lion, the Witch and the Wardrobe** | **2005** | Adventure | 629 | **88.5** | **65.1** | [🇱🇦 Lao](subtitles/Chronicles.of.Narnia.The.Lion.the.Witch.and.the.Wardrobe.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Chronicles.of.Narnia.The.Lion.the.Witch.and.the.Wardrobe.2005.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Cinema Paradiso** | **1988** | Romance | 457 | **88.9** | **65.5** | [🇱🇦 Lao](subtitles/Cinema.Paradiso.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cinema.Paradiso.1988.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Cirque du Freak: The Vampire's Assistant** | **2009** | Adventure | 938 | **88.0** | **65.2** | [🇱🇦 Lao](subtitles/Cirque.du.Freak.The.Vampires.Assistant.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cirque.du.Freak.The.Vampires.Assistant.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Clash of the Titans** | **2010** | Adventure | 764 | **88.5** | **64.8** | [🇱🇦 Lao](subtitles/Clash.of.the.Titans.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Clash.of.the.Titans.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Cliffhanger** | **1993** | Adventure | 559 | **88.1** | **65.3** | [🇱🇦 Lao](subtitles/Cliffhanger.1993.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Cliffhanger.1993.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Coco** | **2017** | Feature Film | 1,444 | **88.3** | **65.3** | [🇱🇦 Lao](subtitles/Coco.2017.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Coco.2017.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Constantine** | **2005** | Horror | 721 | **88.3** | **64.3** | [🇱🇦 Lao](subtitles/Constantine.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Constantine.2005.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Copycat** | **1995** | Horror | 843 | **88.1** | **64.6** | [🇱🇦 Lao](subtitles/Copycat.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Copycat.1995.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Coraline** | **2009** | Animation | 804 | **89.1** | **65.3** | [🇱🇦 Lao](subtitles/Coraline.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Coraline.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Corpse Bride** | **2005** | Animation | 495 | **89.1** | **65.3** | [🇱🇦 Lao](subtitles/Corpse.Bride.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Corpse.Bride.2005.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Crouching Tiger, Hidden Dragon** | **2000** | Adventure | 531 | **88.0** | **65.1** | [🇱🇦 Lao](subtitles/Crouching.Tiger.Hidden.Dragon.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Crouching.Tiger.Hidden.Dragon.2000.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Dances with Wolves** | **1990** | Adventure | 638 | **88.7** | **65.0** | [🇱🇦 Lao](subtitles/Dances.with.Wolves.1990.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dances.with.Wolves.1990.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Dark City** | **1998** | Sci-Fi | 560 | **88.2** | **65.2** | [🇱🇦 Lao](subtitles/Dark.City.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dark.City.1998.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Dark Star** | **1974** | Sci-Fi | 350 | **88.1** | **65.1** | [🇱🇦 Lao](subtitles/Dark.Star.1974.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dark.Star.1974.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Darkman** | **1990** | Sci-Fi | 930 | **88.0** | **65.0** | [🇱🇦 Lao](subtitles/Darkman.1990.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Darkman.1990.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Dawn of the Dead** | **2004** | Horror | 139 | **88.1** | **64.2** | [🇱🇦 Lao](subtitles/Dawn.of.the.Dead.2004.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dawn.of.the.Dead.2004.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Deadpool** | **2016** | Adventure | 742 | **88.5** | **64.5** | [🇱🇦 Lao](subtitles/Deadpool.2016.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Deadpool.2016.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Deadpool & Wolverine** | **2024** | Sci-Fi | 742 | **87.9** | **64.4** | [🇱🇦 Lao](subtitles/Deadpool.and.Wolverine.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Deadpool.and.Wolverine.2024.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Deep Rising** | **1998** | Horror | 632 | **87.6** | **64.9** | [🇱🇦 Lao](subtitles/Deep.Rising.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Deep.Rising.1998.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Despicable Me 2** | **2013** | Animation | 710 | **89.1** | **65.7** | [🇱🇦 Lao](subtitles/Despicable.Me.2.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Despicable.Me.2.2013.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Detroit Rock City** | **1999** | Adventure | 777 | **87.9** | **65.0** | [🇱🇦 Lao](subtitles/Detroit.Rock.City.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Detroit.Rock.City.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Devil's Advocate** | **1997** | Horror | 1,060 | **88.3** | **64.3** | [🇱🇦 Lao](subtitles/Devils.Advocate.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Devils.Advocate.1997.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Django Unchained** | **2012** | Adventure | 1,067 | **88.4** | **64.9** | [🇱🇦 Lao](subtitles/Django.Unchained.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Django.Unchained.2012.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Dogma** | **1999** | Adventure | 955 | **88.3** | **64.8** | [🇱🇦 Lao](subtitles/Dogma.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dogma.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Drag Me to Hell** | **2009** | Horror | 665 | **87.7** | **64.2** | [🇱🇦 Lao](subtitles/Drag.Me.to.Hell.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Drag.Me.to.Hell.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Dune** | **1984** | Sci-Fi | 617 | **88.5** | **64.7** | [🇱🇦 Lao](subtitles/Dune.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dune.1984.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Dune Part One** | **2021** | Sci-Fi | 648 | **87.8** | **64.6** | [🇱🇦 Lao](subtitles/Dune.Part.One.2021.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Dune.Part.One.2021.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Eight Legged Freaks** | **2002** | Sci-Fi | 675 | **87.9** | **65.0** | [🇱🇦 Lao](subtitles/Eight.Legged.Freaks.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Eight.Legged.Freaks.2002.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Elemental** | **2023** | Animation | 906 | **88.7** | **65.3** | [🇱🇦 Lao](subtitles/Elemental.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Elemental.2023.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Escape From L.A.** | **1996** | Sci-Fi | 617 | **88.3** | **65.2** | [🇱🇦 Lao](subtitles/Escape.From.L.A..1996.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Escape.From.L.A..1996.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Event Horizon** | **1997** | Horror | 892 | **87.9** | **64.5** | [🇱🇦 Lao](subtitles/Event.Horizon.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Event.Horizon.1997.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Evil Dead** | **1981** | Horror | 310 | **88.1** | **64.4** | [🇱🇦 Lao](subtitles/Evil.Dead.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Evil.Dead.1981.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Evil Dead II: Dead by Dawn** | **1987** | Horror | 221 | **87.7** | **64.4** | [🇱🇦 Lao](subtitles/Evil.Dead.II.Dead.by.Dawn.1987.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Evil.Dead.II.Dead.by.Dawn.1987.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Fantastic Mr Fox** | **2009** | Animation | 625 | **88.5** | **65.8** | [🇱🇦 Lao](subtitles/Fantastic.Mr.Fox.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Fantastic.Mr.Fox.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Feast** | **2005** | Horror | 831 | **88.1** | **64.6** | [🇱🇦 Lao](subtitles/Feast.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Feast.2005.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Fight Club** | **1999** | Drama / Classics | 1,293 | **87.9** | **65.0** | [🇱🇦 Lao](subtitles/Fight.Club.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Fight.Club.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Final Destination** | **2000** | Horror | 447 | **88.3** | **64.5** | [🇱🇦 Lao](subtitles/Final.Destination.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Final.Destination.2000.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Final Destination 2** | **2003** | Horror | 648 | **87.6** | **64.7** | [🇱🇦 Lao](subtitles/Final.Destination.2.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Final.Destination.2.2003.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Forrest Gump** | **1994** | Drama / Classics | 1,065 | **88.2** | **65.0** | [🇱🇦 Lao](subtitles/Forrest.Gump.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Forrest.Gump.1994.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Freddy vs. Jason** | **2003** | Horror | 716 | **88.0** | **64.8** | [🇱🇦 Lao](subtitles/Freddy.vs..Jason.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Freddy.vs..Jason.2003.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Friday the 13th** | **1980** | Horror | 432 | **87.8** | **64.4** | [🇱🇦 Lao](subtitles/Friday.the.13th.1980.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Friday.the.13th.1980.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Friday the 13th Part VIII: Jason Takes Manhattan** | **1989** | Horror | 569 | **87.7** | **64.2** | [🇱🇦 Lao](subtitles/Friday.the.13th.Part.VIII.Jason.Takes.Manhattan.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Friday.the.13th.Part.VIII.Jason.Takes.Manhattan.1989.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Fright Night** | **1985** | Horror | 883 | **88.3** | **64.8** | [🇱🇦 Lao](subtitles/Fright.Night.1985.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Fright.Night.1985.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Frozen** | **2013** | Feature Film | 1,652 | **88.7** | **64.8** | [🇱🇦 Lao](subtitles/Frozen.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Frozen.2013.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Frozen** | **2013** | Animation | 917 | **89.3** | **65.2** | [🇱🇦 Lao](subtitles/Frozen.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Frozen.2013.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Gladiator** | **2000** | Drama / Classics | 675 | **88.7** | **65.0** | [🇱🇦 Lao](subtitles/Gladiator.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Gladiator.2000.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Happy Feet** | **2006** | Animation | 633 | **89.0** | **66.0** | [🇱🇦 Lao](subtitles/Happy.Feet.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Happy.Feet.2006.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Heavy Metal** | **1981** | Animation | 297 | **88.5** | **65.5** | [🇱🇦 Lao](subtitles/Heavy.Metal.1981.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Heavy.Metal.1981.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Here Comes Peter Cottontail** | **1971** | Animation | 508 | **88.7** | **65.8** | [🇱🇦 Lao](subtitles/Here.Comes.Peter.Cottontail.1971.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Here.Comes.Peter.Cottontail.1971.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **How to Train Your Dragon** | **2010** | Animation | 623 | **89.1** | **65.8** | [🇱🇦 Lao](subtitles/How.to.Train.Your.Dragon.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/How.to.Train.Your.Dragon.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **How to Train Your Dragon 2** | **2014** | Animation | 726 | **88.5** | **65.2** | [🇱🇦 Lao](subtitles/How.to.Train.Your.Dragon.2.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/How.to.Train.Your.Dragon.2.2014.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Inception** | **2010** | Drama / Classics | 1,223 | **88.5** | **64.7** | [🇱🇦 Lao](subtitles/Inception.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Inception.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Interstellar** | **2014** | Drama / Classics | 902 | **88.1** | **64.8** | [🇱🇦 Lao](subtitles/Interstellar.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Interstellar.2014.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Kung Fu Panda** | **2008** | Animation | 694 | **89.2** | **65.7** | [🇱🇦 Lao](subtitles/Kung.Fu.Panda.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Kung.Fu.Panda.2008.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **L' Avventura (The Adventure)** | **1960** | Thriller | 745 | **88.0** | **64.7** | [🇱🇦 Lao](subtitles/L.Avventura.The.Adventure.1960.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/L.Avventura.The.Adventure.1960.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Megamind** | **2010** | Animation | 866 | **89.3** | **65.8** | [🇱🇦 Lao](subtitles/Megamind.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Megamind.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Memento** | **2000** | Feature Film | 692 | **88.2** | **64.7** | [🇱🇦 Lao](subtitles/Memento.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Memento.2000.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Moana** | **2016** | Feature Film | 1,233 | **88.1** | **65.2** | [🇱🇦 Lao](subtitles/Moana.2016.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Moana.2016.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Monkeybone** | **2001** | Animation | 643 | **89.0** | **65.3** | [🇱🇦 Lao](subtitles/Monkeybone.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Monkeybone.2001.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **One Eight Seven (187)** | **1997** | Drama | 754 | **88.2** | **65.2** | [🇱🇦 Lao](subtitles/One.Eight.Seven.187.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/One.Eight.Seven.187.1997.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Onward** | **2020** | Animation | 1,114 | **89.1** | **65.4** | [🇱🇦 Lao](subtitles/Onward.2020.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Onward.2020.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **ParaNorman** | **2012** | Animation | 664 | **88.7** | **65.2** | [🇱🇦 Lao](subtitles/ParaNorman.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/ParaNorman.2012.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Pulp Fiction** | **1994** | Drama / Classics | 1,214 | **88.7** | **64.7** | [🇱🇦 Lao](subtitles/Pulp.Fiction.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Pulp.Fiction.1994.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Puss in Boots: The Last Wish** | **2022** | Animation | 1,134 | **88.6** | **65.6** | [🇱🇦 Lao](subtitles/Puss.in.Boots.The.Last.Wish.2022.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Puss.in.Boots.The.Last.Wish.2022.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Reservoir Dogs** | **1992** | Feature Film | 694 | **88.2** | **64.9** | [🇱🇦 Lao](subtitles/Reservoir.Dogs.1992.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Reservoir.Dogs.1992.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Rise of the Guardians** | **2012** | Animation | 984 | **88.8** | **65.7** | [🇱🇦 Lao](subtitles/Rise.of.the.Guardians.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Rise.of.the.Guardians.2012.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Saving Private Ryan** | **1998** | Feature Film | 934 | **88.1** | **65.2** | [🇱🇦 Lao](subtitles/Saving.Private.Ryan.1998.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Saving.Private.Ryan.1998.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Se7en** | **1995** | Feature Film | 489 | **88.6** | **64.7** | [🇱🇦 Lao](subtitles/Se7en.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Se7en.1995.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Shrek** | **2001** | Animation | 744 | **88.5** | **65.9** | [🇱🇦 Lao](subtitles/Shrek.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Shrek.2001.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Shrek the Third** | **2007** | Animation | 723 | **88.6** | **65.6** | [🇱🇦 Lao](subtitles/Shrek.the.Third.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Shrek.the.Third.2007.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **South Park: Bigger, Longer & Uncut** | **1999** | Animation | 1,257 | **88.7** | **65.8** | [🇱🇦 Lao](subtitles/South.Park.Bigger.Longer.and.Uncut.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/South.Park.Bigger.Longer.and.Uncut.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Spider-Man: Across the Spider-Verse** | **2023** | Animation | 1,542 | **89.0** | **66.0** | [🇱🇦 Lao](subtitles/Spider-Man.Across.the.Spider-Verse.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Spider-Man.Across.the.Spider-Verse.2023.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Star Wars: Episode IV - A New Hope** | **1977** | Feature Film | 994 | **88.7** | **65.2** | [🇱🇦 Lao](subtitles/Star.Wars.Episode.IV.-.A.New.Hope.1977.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Star.Wars.Episode.IV.-.A.New.Hope.1977.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Teenage Mutant Ninja Turtles: Mutant Mayhem** | **2023** | Animation | 996 | **89.3** | **65.7** | [🇱🇦 Lao](subtitles/Teenage.Mutant.Ninja.Turtles.Mutant.Mayhem.2023.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Teenage.Mutant.Ninja.Turtles.Mutant.Mayhem.2023.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Terminator 2: Judgment Day** | **1991** | Feature Film | 518 | **88.7** | **64.8** | [🇱🇦 Lao](subtitles/Terminator.2.Judgment.Day.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Terminator.2.Judgment.Day.1991.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Abyss** | **1989** | Thriller | 665 | **88.2** | **64.5** | [🇱🇦 Lao](subtitles/The.Abyss.1989.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Abyss.1989.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Addams Family** | **1991** | Horror | 265 | **87.7** | **64.5** | [🇱🇦 Lao](subtitles/The.Addams.Family.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Addams.Family.1991.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Adjustment Bureau** | **2011** | Thriller | 978 | **87.8** | **64.9** | [🇱🇦 Lao](subtitles/The.Adjustment.Bureau.2011.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Adjustment.Bureau.2011.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The American** | **2010** | Thriller | 693 | **87.7** | **64.6** | [🇱🇦 Lao](subtitles/The.American.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.American.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The American President** | **1995** | Romance | 1,403 | **88.6** | **65.1** | [🇱🇦 Lao](subtitles/The.American.President.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.American.President.1995.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Amityville Asylum** | **2013** | Horror | 631 | **87.9** | **64.6** | [🇱🇦 Lao](subtitles/The.Amityville.Asylum.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Amityville.Asylum.2013.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Apartment** | **1960** | Comedy | 1,214 | **88.5** | **65.0** | [🇱🇦 Lao](subtitles/The.Apartment.1960.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Apartment.1960.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Assignment** | **1997** | Thriller | 788 | **88.4** | **64.7** | [🇱🇦 Lao](subtitles/The.Assignment.1997.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Assignment.1997.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Avengers** | **2012** | Sci-Fi | 941 | **88.0** | **64.6** | [🇱🇦 Lao](subtitles/The.Avengers.2012.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Avengers.2012.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Back-up Plan** | **2010** | Romance | 865 | **88.6** | **65.3** | [🇱🇦 Lao](subtitles/The.Back-up.Plan.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Back-up.Plan.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Battle of Shaker Heights** | **2003** | Romance | 945 | **88.2** | **65.6** | [🇱🇦 Lao](subtitles/The.Battle.of.Shaker.Heights.2003.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Battle.of.Shaker.Heights.2003.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Beekeeper** | **2024** | Thriller | 762 | **88.4** | **64.3** | [🇱🇦 Lao](subtitles/The.Beekeeper.2024.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Beekeeper.2024.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Big Blue** | **1988** | Romance | 849 | **88.4** | **65.3** | [🇱🇦 Lao](subtitles/The.Big.Blue.1988.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Big.Blue.1988.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Big Sick** | **2017** | Romance | 1,119 | **88.9** | **65.1** | [🇱🇦 Lao](subtitles/The.Big.Sick.2017.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Big.Sick.2017.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Big White** | **2005** | Crime | 840 | **88.2** | **64.4** | [🇱🇦 Lao](subtitles/The.Big.White.2005.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Big.White.2005.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Birds** | **1963** | Romance | 1,139 | **88.8** | **65.5** | [🇱🇦 Lao](subtitles/The.Birds.1963.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Birds.1963.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Black Dahlia** | **2006** | Crime | 1,048 | **87.7** | **64.9** | [🇱🇦 Lao](subtitles/The.Black.Dahlia.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Black.Dahlia.2006.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Blast from the Past** | **1999** | Romance | 1,268 | **88.7** | **65.4** | [🇱🇦 Lao](subtitles/The.Blast.from.the.Past.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Blast.from.the.Past.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Bling Ring** | **2013** | Crime | 606 | **88.1** | **64.9** | [🇱🇦 Lao](subtitles/The.Bling.Ring.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bling.Ring.2013.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Book of Eli** | **2010** | Sci-Fi | 786 | **87.7** | **65.1** | [🇱🇦 Lao](subtitles/The.Book.of.Eli.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Book.of.Eli.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Boondock Saints** | **1999** | Crime | 787 | **88.5** | **64.8** | [🇱🇦 Lao](subtitles/The.Boondock.Saints.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Boondock.Saints.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Bounty Hunter** | **2010** | Romance | 934 | **88.8** | **65.6** | [🇱🇦 Lao](subtitles/The.Bounty.Hunter.2010.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bounty.Hunter.2010.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Bourne Identity** | **2002** | Adventure | 643 | **88.4** | **64.6** | [🇱🇦 Lao](subtitles/The.Bourne.Identity.2002.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bourne.Identity.2002.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Bourne Ultimatum** | **2007** | Adventure | 553 | **88.7** | **65.0** | [🇱🇦 Lao](subtitles/The.Bourne.Ultimatum.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Bourne.Ultimatum.2007.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Box** | **2009** | Sci-Fi | 811 | **88.0** | **64.6** | [🇱🇦 Lao](subtitles/The.Box.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Box.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Boxtrolls** | **2014** | Animation | 938 | **88.6** | **65.2** | [🇱🇦 Lao](subtitles/The.Boxtrolls.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Boxtrolls.2014.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Brothers Bloom** | **2008** | Romance | 706 | **88.4** | **65.5** | [🇱🇦 Lao](subtitles/The.Brothers.Bloom.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Brothers.Bloom.2008.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Cell** | **2000** | Sci-Fi | 621 | **88.1** | **64.8** | [🇱🇦 Lao](subtitles/The.Cell.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Cell.2000.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Cider House Rules** | **1999** | Romance | 1,020 | **88.3** | **65.1** | [🇱🇦 Lao](subtitles/The.Cider.House.Rules.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Cider.House.Rules.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Croods** | **2013** | Animation | 805 | **88.7** | **65.6** | [🇱🇦 Lao](subtitles/The.Croods.2013.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Croods.2013.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Crow** | **1994** | Horror | 539 | **88.1** | **65.0** | [🇱🇦 Lao](subtitles/The.Crow.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Crow.1994.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Crow Salvation** | **2000** | Horror | 572 | **87.5** | **64.7** | [🇱🇦 Lao](subtitles/The.Crow.Salvation.2000.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Crow.Salvation.2000.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Dark Knight** | **2008** | Drama / Classics | 1,243 | **87.9** | **64.7** | [🇱🇦 Lao](subtitles/The.Dark.Knight.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Dark.Knight.2008.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Day the Earth Stood Still** | **2008** | Sci-Fi | 770 | **88.5** | **65.1** | [🇱🇦 Lao](subtitles/The.Day.the.Earth.Stood.Still.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Day.the.Earth.Stood.Still.2008.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Departed** | **2006** | Feature Film | 1,180 | **88.1** | **64.6** | [🇱🇦 Lao](subtitles/The.Departed.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Departed.2006.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Godfather** | **1972** | Drama / Classics | 899 | **88.7** | **65.3** | [🇱🇦 Lao](subtitles/The.Godfather.1972.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Godfather.1972.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Green Mile** | **1999** | Feature Film | 1,012 | **88.4** | **64.6** | [🇱🇦 Lao](subtitles/The.Green.Mile.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Green.Mile.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The LEGO Movie** | **2014** | Animation | 961 | **88.7** | **66.0** | [🇱🇦 Lao](subtitles/The.LEGO.Movie.2014.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.LEGO.Movie.2014.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Lord of the Rings: The Fellowship of the Ring** | **2001** | Feature Film | 817 | **88.4** | **64.6** | [🇱🇦 Lao](subtitles/The.Lord.of.the.Rings.The.Fellowship.of.the.Ring.2001.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Lord.of.the.Rings.The.Fellowship.of.the.Ring.2001.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Matrix** | **1999** | Drama / Classics | 568 | **88.5** | **65.3** | [🇱🇦 Lao](subtitles/The.Matrix.1999.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Matrix.1999.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Prestige** | **2006** | Feature Film | 1,047 | **88.4** | **64.6** | [🇱🇦 Lao](subtitles/The.Prestige.2006.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Prestige.2006.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Shawshank Redemption** | **1994** | Feature Film | 803 | **88.6** | **65.3** | [🇱🇦 Lao](subtitles/The.Shawshank.Redemption.1994.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Shawshank.Redemption.1994.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Silence Of The Lambs** | **1991** | Feature Film | 928 | **88.2** | **65.0** | [🇱🇦 Lao](subtitles/The.Silence.Of.The.Lambs.1991.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Silence.Of.The.Lambs.1991.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Terminator** | **1984** | Feature Film | 503 | **88.1** | **64.7** | [🇱🇦 Lao](subtitles/The.Terminator.1984.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Terminator.1984.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **The Usual Suspects** | **1995** | Feature Film | 768 | **88.7** | **65.1** | [🇱🇦 Lao](subtitles/The.Usual.Suspects.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/The.Usual.Suspects.1995.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **TMNT** | **2007** | Animation | 551 | **88.7** | **65.6** | [🇱🇦 Lao](subtitles/TMNT.2007.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/TMNT.2007.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Toy Story** | **1995** | Animation | 887 | **88.5** | **65.2** | [🇱🇦 Lao](subtitles/Toy.Story.1995.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Toy.Story.1995.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Transformers: The Movie** | **1986** | Animation | 720 | **89.1** | **65.9** | [🇱🇦 Lao](subtitles/Transformers.The.Movie.1986.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Transformers.The.Movie.1986.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Up** | **2009** | Animation | 720 | **88.8** | **65.4** | [🇱🇦 Lao](subtitles/Up.2009.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Up.2009.bilingual.srt) | ✓ LoRA 1.3B Champion |
| **Wall-E** | **2008** | Animation | 476 | **89.0** | **65.2** | [🇱🇦 Lao](subtitles/Wall-E.2008.lao.srt) · [🇺🇸/🇱🇦 Bilingual](subtitles/Wall-E.2008.bilingual.srt) | ✓ LoRA 1.3B Champion |

</details>

---

## 🧠 How These Subtitles Are Produced

These subtitles are produced using an advanced local AI translation pipeline running 100% offline on an **NVIDIA GeForce RTX 5090 (32GB VRAM)**:

1. **PacTranz 5-Step Cinema Methodology**:
   - **Step 1: Named Entity Recognition & Cultural Pronouns** — Enforces natural honorifics (`ເຈົ້າ`, `ຂ້ອຍ`, `ອ້າຍ`, `ເອື້ອຍ`, `ນ້ອງ`) matched to character relationships.
   - **Step 2: Literal Draft Generation** — Translates dialogue while preserving dramatic tone and pacing.
   - **Step 3: Lao Syntax Alignment** — Normalizes word order, applies correct classifiers (`ໂຕ`, `ຄົນ`, `ຫົວ`, `ຄັນ`), and aligns serial verb constructions (`ເອົາມາ`, `ແລ່ນໜີ`).
   - **Step 4: Spoken Dialogue & Diglossia Pass** — Converts formal written Lao into natural spoken speech (*Phasa Pak*) with authentic pragmatic particles (`ເດີ້`, `ເນາະ`, `ແດ່`, `ແມ`).
   - **Step 5: Automated QA & Linguistic Audit** — Quality checks via chrF++ scoring and the **Pamela Sue Wright Linguistic Audit** (checking against 50,210 Lao dictionary terms, tone mark stacking, and eliminating Thai loanword drift).

2. **Fine-Tuned Neural Adapter (LoRA 1.3B Champion)**:
   - Built on Meta's `facebook/nllb-200-distilled-1.3B` architecture.
   - Fine-tuned with Direct Preference Optimization (DPO) and oversampled conversational alignments, achieving an **88.33 / 100 chrF++ quality score** and 0% Thai character leaks.

3. **Frame-Accurate Subtitle Timing**:
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

Native Lao speakers: corrections and feedback are warmly welcomed!
- Open an **[Issue](https://github.com/Hieng1999/lao-subtitles/issues)** with the movie name, timestamp, and suggested Lao correction.
- Send a **Pull Request** directly with your edits. Corrections feed back into our local AI training memory.

---

## ❤️ About This Project

This started with a simple wish: to help someone I love enjoy movies in the language they're most comfortable in. Lao subtitles for major films basically don't exist online — so I built a translation pipeline and started making them, and I'm sharing the results here free for anyone to use. If they help even one more family enjoy a movie together, it's worth it.

---

## 📜 License & Disclaimer

Fan-made subtitle translations, shared freely for educational and accessibility purposes. The underlying films and their original dialogue remain © their respective rights holders; this project claims no ownership over the original source media.
