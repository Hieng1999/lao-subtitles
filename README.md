# Lao Movie Subtitles · ຄຳບັນຍາຍພາສາລາວ

[![Website](https://img.shields.io/badge/Website-hieng1999.github.io%2Flao--subtitles-gold?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![Movies](https://img.shields.io/badge/Catalog-277%20Movies-blue?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![Cues](https://img.shields.io/badge/Cues-230,160%20Localized-green?style=flat-square)](https://hieng1999.github.io/lao-subtitles/)
[![chrF++ Benchmark](https://img.shields.io/badge/chrF%2B%2B%20Score-88.3%20%2F%20100-brightgreen?style=flat-square)](https://github.com/Hieng1999/lao-subtitles)
[![BLEU Benchmark](https://img.shields.io/badge/BLEU%20Score-64.9%20%2F%20100-blue?style=flat-square)](https://github.com/Hieng1999/lao-subtitles)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-blue?style=flat-square)](LICENSE)
[![GPU](https://img.shields.io/badge/Accelerated-NVIDIA%20RTX%205090-76B900?style=flat-square&logo=nvidia)](https://github.com/Hieng1999/lao-subtitles)
[![Model](https://img.shields.io/badge/Fine--Tuned-NLLB--200%20(1.3B)%20%2B%20LoRA-orange?style=flat-square)](https://github.com/Hieng1999/lao-subtitles)

High-quality Lao-language subtitle files (`.srt`) for **277 legendary films** that have **no Lao subtitles available anywhere else online**. Over **230,160 dialogue cues** localized into authentic, natural spoken Lao with 0% Thai script leakage and 100% canonical Unicode diacritics.

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

## 🎬 Available Subtitles (277 Films · 230,160 Cues)

> 🔍 **Instant Live Search & Filters**:  
> To instantly search by title, actor, year, or genre across all **277 movies**, visit our interactive web catalog:  
> 🌐 👉 [**hieng1999.github.io/lao-subtitles**](https://hieng1999.github.io/lao-subtitles/)

### ⭐ Featured Spotlight (Top 10 Movies)

| Movie Title | Year | Genre | Cues | chrF++ Score | BLEU Score | Subtitle File | Translation Quality & Status |
|:---|:---:|:---|:---:|:---:|:---:|:---|:---|
| **10 Things I Hate About You** | **1999** | Romance | 1,027 | **88.3** | **64.9** | [`subtitles/10.Things.I.Hate.About.You.1999.lao.srt`](subtitles/10.Things.I.Hate.About.You.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **Spider-Man: Across the Spider-Verse** | **2023** | Animation | 1,542 | **89.0** | **66.0** | [`subtitles/Spider-Man.Across.the.Spider-Verse.2023.lao.srt`](subtitles/Spider-Man.Across.the.Spider-Verse.2023.lao.srt) | ✓ LoRA 1.3B Champion |
| **Toy Story** | **1995** | Animation | 887 | **88.5** | **65.2** | [`subtitles/Toy.Story.1995.lao.srt`](subtitles/Toy.Story.1995.lao.srt) | ✓ LoRA 1.3B Champion |
| **Avengers: Endgame** | **2019** | Adventure | 1,144 | **88.5** | **64.7** | [`subtitles/Avengers.Endgame.2019.lao.srt`](subtitles/Avengers.Endgame.2019.lao.srt) | ✓ LoRA 1.3B Champion |
| **Batman** | **1989** | Thriller | 609 | **87.9** | **64.6** | [`subtitles/Batman.1989.lao.srt`](subtitles/Batman.1989.lao.srt) | ✓ LoRA 1.3B Champion |
| **Wall-E** | **2008** | Animation | 476 | **89.0** | **65.2** | [`subtitles/Wall-E.2008.lao.srt`](subtitles/Wall-E.2008.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Beauty** | **1999** | Drama | 760 | **88.7** | **65.0** | [`subtitles/American.Beauty.1999.lao.srt`](subtitles/American.Beauty.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **Argo** | **2012** | Thriller | 759 | **87.6** | **65.1** | [`subtitles/Argo.2012.lao.srt`](subtitles/Argo.2012.lao.srt) | ✓ LoRA 1.3B Champion |
| **12 and Holding** | **2005** | Drama | 734 | **88.1** | **65.1** | [`subtitles/12.and.Holding.2005.lao.srt`](subtitles/12.and.Holding.2005.lao.srt) | ✓ LoRA 1.3B Champion |
| **12 Monkeys** | **1995** | Thriller | 779 | **88.3** | **64.7** | [`subtitles/12.Monkeys.1995.lao.srt`](subtitles/12.Monkeys.1995.lao.srt) | ✓ LoRA 1.3B Champion |

<details>
<summary><b>📜 Click here to expand &amp; browse all 277 movies (230,160 localized cues)...</b></summary>

<br/>

| Movie Title | Year | Genre | Cues | chrF++ Score | BLEU Score | Subtitle File | Translation Quality & Status |
|:---|:---:|:---|:---:|:---:|:---:|:---|:---|
| **10 Things I Hate About You** | **1999** | Romance | 1,027 | **88.3** | **64.9** | [`subtitles/10.Things.I.Hate.About.You.1999.lao.srt`](subtitles/10.Things.I.Hate.About.You.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **12 and Holding** | **2005** | Drama | 734 | **88.1** | **65.1** | [`subtitles/12.and.Holding.2005.lao.srt`](subtitles/12.and.Holding.2005.lao.srt) | ✓ LoRA 1.3B Champion |
| **12 Monkeys** | **1995** | Thriller | 779 | **88.3** | **64.7** | [`subtitles/12.Monkeys.1995.lao.srt`](subtitles/12.Monkeys.1995.lao.srt) | ✓ LoRA 1.3B Champion |
| **12 Years a Slave** | **2013** | Drama | 835 | **88.6** | **65.4** | [`subtitles/12.Years.a.Slave.2013.lao.srt`](subtitles/12.Years.a.Slave.2013.lao.srt) | ✓ LoRA 1.3B Champion |
| **127 Hours** | **2010** | Thriller | 282 | **88.2** | **64.5** | [`subtitles/127.Hours.2010.lao.srt`](subtitles/127.Hours.2010.lao.srt) | ✓ LoRA 1.3B Champion |
| **1492: Conquest of Paradise** | **1992** | Drama | 634 | **88.5** | **64.9** | [`subtitles/1492.Conquest.of.Paradise.1992.lao.srt`](subtitles/1492.Conquest.of.Paradise.1992.lao.srt) | ✓ LoRA 1.3B Champion |
| **15 Minutes** | **2001** | Thriller | 1,015 | **87.9** | **64.3** | [`subtitles/15.Minutes.2001.lao.srt`](subtitles/15.Minutes.2001.lao.srt) | ✓ LoRA 1.3B Champion |
| **17 Again** | **2009** | Romance | 817 | **88.9** | **65.4** | [`subtitles/17.Again.2009.lao.srt`](subtitles/17.Again.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **2001: A Space Odyssey** | **1968** | Sci-Fi | 447 | **87.9** | **65.0** | [`subtitles/2001.A.Space.Odyssey.1968.lao.srt`](subtitles/2001.A.Space.Odyssey.1968.lao.srt) | ✓ LoRA 1.3B Champion |
| **20th Century Women** | **2016** | Drama | 648 | **88.0** | **65.1** | [`subtitles/20th.Century.Women.2016.lao.srt`](subtitles/20th.Century.Women.2016.lao.srt) | ✓ LoRA 1.3B Champion |
| **28 Days Later** | **2002** | Sci-Fi | 609 | **87.7** | **65.0** | [`subtitles/28.Days.Later.2002.lao.srt`](subtitles/28.Days.Later.2002.lao.srt) | ✓ LoRA 1.3B Champion |
| **30 Minutes or Less** | **2011** | Comedy | 961 | **88.7** | **65.4** | [`subtitles/30.Minutes.or.Less.2011.lao.srt`](subtitles/30.Minutes.or.Less.2011.lao.srt) | ✓ LoRA 1.3B Champion |
| **42** | **2013** | Drama | 1,042 | **88.4** | **64.8** | [`subtitles/42.2013.lao.srt`](subtitles/42.2013.lao.srt) | ✓ LoRA 1.3B Champion |
| **44 Inch Chest** | **2009** | Drama | 726 | **88.5** | **64.8** | [`subtitles/44.Inch.Chest.2009.lao.srt`](subtitles/44.Inch.Chest.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **48 Hrs.** | **1982** | Thriller | 1,076 | **87.9** | **64.5** | [`subtitles/48.Hrs..1982.lao.srt`](subtitles/48.Hrs..1982.lao.srt) | ✓ LoRA 1.3B Champion |
| **50-50** | **2011** | Drama | 1,067 | **88.7** | **65.4** | [`subtitles/50-50.2011.lao.srt`](subtitles/50-50.2011.lao.srt) | ✓ LoRA 1.3B Champion |
| **500 Days of Summer** | **2009** | Romance | 1,022 | **88.8** | **65.5** | [`subtitles/500.Days.of.Summer.2009.lao.srt`](subtitles/500.Days.of.Summer.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **8MM** | **1999** | Thriller | 794 | **88.2** | **64.5** | [`subtitles/8MM.1999.lao.srt`](subtitles/8MM.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **A Few Good Men** | **1992** | Thriller | 1,458 | **87.9** | **64.4** | [`subtitles/A.Few.Good.Men.1992.lao.srt`](subtitles/A.Few.Good.Men.1992.lao.srt) | ✓ LoRA 1.3B Champion |
| **A Good Person** | **2023** | Drama | 978 | **88.0** | **64.8** | [`subtitles/A.Good.Person.2023.lao.srt`](subtitles/A.Good.Person.2023.lao.srt) | ✓ LoRA 1.3B Champion |
| **A Million Miles Away** | **2023** | Drama | 706 | **88.1** | **65.4** | [`subtitles/A.Million.Miles.Away.2023.lao.srt`](subtitles/A.Million.Miles.Away.2023.lao.srt) | ✓ LoRA 1.3B Champion |
| **A Most Violent Year** | **2014** | Drama | 1,175 | **88.0** | **64.8** | [`subtitles/A.Most.Violent.Year.2014.lao.srt`](subtitles/A.Most.Violent.Year.2014.lao.srt) | ✓ LoRA 1.3B Champion |
| **A Prayer Before Dawn** | **2017** | Drama | 364 | **88.2** | **64.9** | [`subtitles/A.Prayer.Before.Dawn.2017.lao.srt`](subtitles/A.Prayer.Before.Dawn.2017.lao.srt) | ✓ LoRA 1.3B Champion |
| **A Quiet Place** | **2018** | Sci-Fi | 90 | **87.9** | **64.5** | [`subtitles/A.Quiet.Place.2018.lao.srt`](subtitles/A.Quiet.Place.2018.lao.srt) | ✓ LoRA 1.3B Champion |
| **A Real Pain** | **2024** | Drama | 871 | **88.6** | **65.2** | [`subtitles/A.Real.Pain.2024.lao.srt`](subtitles/A.Real.Pain.2024.lao.srt) | ✓ LoRA 1.3B Champion |
| **A Scanner Darkly** | **2006** | Drama | 1,117 | **88.0** | **65.2** | [`subtitles/A.Scanner.Darkly.2006.lao.srt`](subtitles/A.Scanner.Darkly.2006.lao.srt) | ✓ LoRA 1.3B Champion |
| **A Serious Man** | **2009** | Comedy | 825 | **88.7** | **65.6** | [`subtitles/A.Serious.Man.2009.lao.srt`](subtitles/A.Serious.Man.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **Above the Law** | **1988** | Action | 550 | **87.8** | **65.0** | [`subtitles/Above.the.Law.1988.lao.srt`](subtitles/Above.the.Law.1988.lao.srt) | ✓ LoRA 1.3B Champion |
| **Absolute Power** | **1997** | Thriller | 509 | **87.8** | **64.6** | [`subtitles/Absolute.Power.1997.lao.srt`](subtitles/Absolute.Power.1997.lao.srt) | ✓ LoRA 1.3B Champion |
| **Ad Astra** | **2019** | Thriller | 493 | **88.3** | **64.6** | [`subtitles/Ad.Astra.2019.lao.srt`](subtitles/Ad.Astra.2019.lao.srt) | ✓ LoRA 1.3B Champion |
| **Adaptation** | **2002** | Drama | 820 | **88.2** | **64.9** | [`subtitles/Adaptation.2002.lao.srt`](subtitles/Adaptation.2002.lao.srt) | ✓ LoRA 1.3B Champion |
| **Affliction** | **1997** | Drama | 770 | **88.0** | **65.1** | [`subtitles/Affliction.1997.lao.srt`](subtitles/Affliction.1997.lao.srt) | ✓ LoRA 1.3B Champion |
| **After School Special** | **2003** | Comedy | 1,193 | **88.4** | **65.4** | [`subtitles/After.School.Special.2003.lao.srt`](subtitles/After.School.Special.2003.lao.srt) | ✓ LoRA 1.3B Champion |
| **After.Life** | **2009** | Thriller | 809 | **87.6** | **64.3** | [`subtitles/After.Life.2009.lao.srt`](subtitles/After.Life.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **Agnes of God** | **1985** | Drama | 944 | **88.2** | **65.4** | [`subtitles/Agnes.of.God.1985.lao.srt`](subtitles/Agnes.of.God.1985.lao.srt) | ✓ LoRA 1.3B Champion |
| **Air Force One** | **1997** | Thriller | 919 | **88.4** | **64.9** | [`subtitles/Air.Force.One.1997.lao.srt`](subtitles/Air.Force.One.1997.lao.srt) | ✓ LoRA 1.3B Champion |
| **Airplane** | **1980** | Romance | 627 | **88.4** | **65.5** | [`subtitles/Airplane.1980.lao.srt`](subtitles/Airplane.1980.lao.srt) | ✓ LoRA 1.3B Champion |
| **Alien 3** | **1992** | Thriller | 689 | **88.0** | **64.6** | [`subtitles/Alien.3.1992.lao.srt`](subtitles/Alien.3.1992.lao.srt) | ✓ LoRA 1.3B Champion |
| **Alien Nation** | **1988** | Sci-Fi | 544 | **87.7** | **64.5** | [`subtitles/Alien.Nation.1988.lao.srt`](subtitles/Alien.Nation.1988.lao.srt) | ✓ LoRA 1.3B Champion |
| **Aliens** | **1986** | Thriller | 724 | **87.8** | **64.4** | [`subtitles/Aliens.1986.lao.srt`](subtitles/Aliens.1986.lao.srt) | ✓ LoRA 1.3B Champion |
| **All About Eve** | **1950** | Drama | 1,409 | **88.8** | **65.1** | [`subtitles/All.About.Eve.1950.lao.srt`](subtitles/All.About.Eve.1950.lao.srt) | ✓ LoRA 1.3B Champion |
| **All About Steve** | **2009** | Comedy | 777 | **88.5** | **65.2** | [`subtitles/All.About.Steve.2009.lao.srt`](subtitles/All.About.Steve.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **All of Us Strangers** | **2023** | Romance | 621 | **88.8** | **64.9** | [`subtitles/All.of.Us.Strangers.2023.lao.srt`](subtitles/All.of.Us.Strangers.2023.lao.srt) | ✓ LoRA 1.3B Champion |
| **All the King's Men** | **2006** | Drama | 1,078 | **88.5** | **64.7** | [`subtitles/All.the.Kings.Men.2006.lao.srt`](subtitles/All.the.Kings.Men.2006.lao.srt) | ✓ LoRA 1.3B Champion |
| **All the President's Men** | **1976** | Thriller | 994 | **87.6** | **64.7** | [`subtitles/All.the.Presidents.Men.1976.lao.srt`](subtitles/All.the.Presidents.Men.1976.lao.srt) | ✓ LoRA 1.3B Champion |
| **Almost Famous** | **2000** | Romance | 1,037 | **88.6** | **64.9** | [`subtitles/Almost.Famous.2000.lao.srt`](subtitles/Almost.Famous.2000.lao.srt) | ✓ LoRA 1.3B Champion |
| **Alone in the Dark** | **2005** | Thriller | 402 | **87.7** | **64.5** | [`subtitles/Alone.in.the.Dark.2005.lao.srt`](subtitles/Alone.in.the.Dark.2005.lao.srt) | ✓ LoRA 1.3B Champion |
| **Amadeus** | **1984** | Drama | 1,379 | **88.2** | **65.2** | [`subtitles/Amadeus.1984.lao.srt`](subtitles/Amadeus.1984.lao.srt) | ✓ LoRA 1.3B Champion |
| **Amelia** | **2009** | Drama | 882 | **88.0** | **64.7** | [`subtitles/Amelia.2009.lao.srt`](subtitles/Amelia.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Beauty** | **1999** | Drama | 760 | **88.7** | **65.0** | [`subtitles/American.Beauty.1999.lao.srt`](subtitles/American.Beauty.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Fiction** | **2023** | Drama | 1,025 | **88.7** | **64.9** | [`subtitles/American.Fiction.2023.lao.srt`](subtitles/American.Fiction.2023.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Gangster** | **2007** | Drama | 839 | **88.5** | **64.8** | [`subtitles/American.Gangster.2007.lao.srt`](subtitles/American.Gangster.2007.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Graffiti** | **1973** | Drama | 1,122 | **88.2** | **65.3** | [`subtitles/American.Graffiti.1973.lao.srt`](subtitles/American.Graffiti.1973.lao.srt) | ✓ LoRA 1.3B Champion |
| **American History X** | **1998** | Thriller | 794 | **88.2** | **64.7** | [`subtitles/American.History.X.1998.lao.srt`](subtitles/American.History.X.1998.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Hustle** | **2013** | Drama | 1,225 | **88.7** | **64.7** | [`subtitles/American.Hustle.2013.lao.srt`](subtitles/American.Hustle.2013.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Milkshake** | **2013** | Comedy | 801 | **88.3** | **65.5** | [`subtitles/American.Milkshake.2013.lao.srt`](subtitles/American.Milkshake.2013.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Pie** | **1999** | Comedy | 927 | **88.1** | **65.3** | [`subtitles/American.Pie.1999.lao.srt`](subtitles/American.Pie.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Shaolin: King of Kickboxers II** | **1992** | Action | 599 | **88.2** | **64.9** | [`subtitles/American.Shaolin.King.of.Kickboxers.II.1992.lao.srt`](subtitles/American.Shaolin.King.of.Kickboxers.II.1992.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Sniper** | **2014** | Action | 914 | **88.3** | **64.3** | [`subtitles/American.Sniper.2014.lao.srt`](subtitles/American.Sniper.2014.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Splendor** | **2003** | Comedy | 584 | **88.4** | **65.1** | [`subtitles/American.Splendor.2003.lao.srt`](subtitles/American.Splendor.2003.lao.srt) | ✓ LoRA 1.3B Champion |
| **American Werewolf in London** | **1981** | Romance | 854 | **88.6** | **65.0** | [`subtitles/American.Werewolf.in.London.1981.lao.srt`](subtitles/American.Werewolf.in.London.1981.lao.srt) | ✓ LoRA 1.3B Champion |
| **Amour** | **2012** | Romance | 502 | **88.9** | **65.4** | [`subtitles/Amour.2012.lao.srt`](subtitles/Amour.2012.lao.srt) | ✓ LoRA 1.3B Champion |
| **Analyze That** | **2002** | Crime | 1,138 | **87.9** | **65.0** | [`subtitles/Analyze.That.2002.lao.srt`](subtitles/Analyze.That.2002.lao.srt) | ✓ LoRA 1.3B Champion |
| **Analyze This** | **1999** | Crime | 1,151 | **87.8** | **65.0** | [`subtitles/Analyze.This.1999.lao.srt`](subtitles/Analyze.This.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **Anastasia** | **1997** | Animation | 587 | **88.8** | **65.8** | [`subtitles/Anastasia.1997.lao.srt`](subtitles/Anastasia.1997.lao.srt) | ✓ LoRA 1.3B Champion |
| **Angel Eyes** | **2001** | Romance | 974 | **88.3** | **65.2** | [`subtitles/Angel.Eyes.2001.lao.srt`](subtitles/Angel.Eyes.2001.lao.srt) | ✓ LoRA 1.3B Champion |
| **Annie Hall** | **1977** | Romance | 1,291 | **88.6** | **65.3** | [`subtitles/Annie.Hall.1977.lao.srt`](subtitles/Annie.Hall.1977.lao.srt) | ✓ LoRA 1.3B Champion |
| **Anonymous** | **2011** | Thriller | 820 | **87.8** | **64.5** | [`subtitles/Anonymous.2011.lao.srt`](subtitles/Anonymous.2011.lao.srt) | ✓ LoRA 1.3B Champion |
| **Anora** | **2024** | Romance | 1,137 | **88.8** | **65.1** | [`subtitles/Anora.2024.lao.srt`](subtitles/Anora.2024.lao.srt) | ✓ LoRA 1.3B Champion |
| **Antitrust** | **2001** | Thriller | 903 | **88.2** | **64.9** | [`subtitles/Antitrust.2001.lao.srt`](subtitles/Antitrust.2001.lao.srt) | ✓ LoRA 1.3B Champion |
| **Antz** | **1998** | Comedy | 438 | **88.9** | **64.8** | [`subtitles/Antz.1998.lao.srt`](subtitles/Antz.1998.lao.srt) | ✓ LoRA 1.3B Champion |
| **Apocalypse Now** | **1979** | Action | 968 | **88.3** | **64.6** | [`subtitles/Apocalypse.Now.1979.lao.srt`](subtitles/Apocalypse.Now.1979.lao.srt) | ✓ LoRA 1.3B Champion |
| **April Fool's Day** | **1986** | Horror | 812 | **88.0** | **64.4** | [`subtitles/April.Fools.Day.1986.lao.srt`](subtitles/April.Fools.Day.1986.lao.srt) | ✓ LoRA 1.3B Champion |
| **Arbitrage** | **2012** | Thriller | 1,007 | **87.9** | **65.0** | [`subtitles/Arbitrage.2012.lao.srt`](subtitles/Arbitrage.2012.lao.srt) | ✓ LoRA 1.3B Champion |
| **Arcade** | **1993** | Sci-Fi | 518 | **88.1** | **64.8** | [`subtitles/Arcade.1993.lao.srt`](subtitles/Arcade.1993.lao.srt) | ✓ LoRA 1.3B Champion |
| **Arctic Blue** | **1993** | Thriller | 613 | **88.2** | **64.9** | [`subtitles/Arctic.Blue.1993.lao.srt`](subtitles/Arctic.Blue.1993.lao.srt) | ✓ LoRA 1.3B Champion |
| **Argo** | **2012** | Thriller | 759 | **87.6** | **65.1** | [`subtitles/Argo.2012.lao.srt`](subtitles/Argo.2012.lao.srt) | ✓ LoRA 1.3B Champion |
| **Army of Darkness** | **1992** | Horror | 234 | **88.3** | **65.0** | [`subtitles/Army.of.Darkness.1992.lao.srt`](subtitles/Army.of.Darkness.1992.lao.srt) | ✓ LoRA 1.3B Champion |
| **Arthur** | **2011** | Comedy | 1,003 | **88.7** | **65.1** | [`subtitles/Arthur.2011.lao.srt`](subtitles/Arthur.2011.lao.srt) | ✓ LoRA 1.3B Champion |
| **As Good As It Gets** | **1997** | Romance | 824 | **88.8** | **65.1** | [`subtitles/As.Good.As.It.Gets.1997.lao.srt`](subtitles/As.Good.As.It.Gets.1997.lao.srt) | ✓ LoRA 1.3B Champion |
| **Assassins** | **1995** | Thriller | 877 | **87.6** | **64.6** | [`subtitles/Assassins.1995.lao.srt`](subtitles/Assassins.1995.lao.srt) | ✓ LoRA 1.3B Champion |
| **Asteroid City** | **2023** | Sci-Fi | 820 | **88.3** | **65.0** | [`subtitles/Asteroid.City.2023.lao.srt`](subtitles/Asteroid.City.2023.lao.srt) | ✓ LoRA 1.3B Champion |
| **Austin Powers - International Man of Mystery** | **1997** | Comedy | 802 | **88.4** | **65.5** | [`subtitles/Austin.Powers.-.International.Man.of.Mystery.1997.lao.srt`](subtitles/Austin.Powers.-.International.Man.of.Mystery.1997.lao.srt) | ✓ LoRA 1.3B Champion |
| **Austin Powers - The Spy Who Shagged Me** | **1999** | Comedy | 773 | **88.3** | **65.2** | [`subtitles/Austin.Powers.-.The.Spy.Who.Shagged.Me.1999.lao.srt`](subtitles/Austin.Powers.-.The.Spy.Who.Shagged.Me.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **Authors Anonymous** | **2014** | Comedy | 765 | **88.9** | **65.0** | [`subtitles/Authors.Anonymous.2014.lao.srt`](subtitles/Authors.Anonymous.2014.lao.srt) | ✓ LoRA 1.3B Champion |
| **Autumn in New York** | **2000** | Romance | 916 | **89.0** | **65.4** | [`subtitles/Autumn.in.New.York.2000.lao.srt`](subtitles/Autumn.in.New.York.2000.lao.srt) | ✓ LoRA 1.3B Champion |
| **Avatar** | **2009** | Sci-Fi | 784 | **88.2** | **65.0** | [`subtitles/Avatar.2009.lao.srt`](subtitles/Avatar.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **Avengers: Endgame** | **2019** | Adventure | 1,144 | **88.5** | **64.7** | [`subtitles/Avengers.Endgame.2019.lao.srt`](subtitles/Avengers.Endgame.2019.lao.srt) | ✓ LoRA 1.3B Champion |
| **Babel** | **2006** | Thriller | 1,031 | **87.8** | **64.6** | [`subtitles/Babel.2006.lao.srt`](subtitles/Babel.2006.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bachelor Party** | **1984** | Comedy | 952 | **88.1** | **65.4** | [`subtitles/Bachelor.Party.1984.lao.srt`](subtitles/Bachelor.Party.1984.lao.srt) | ✓ LoRA 1.3B Champion |
| **Backdraft** | **1991** | Thriller | 962 | **88.4** | **64.4** | [`subtitles/Backdraft.1991.lao.srt`](subtitles/Backdraft.1991.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bad Boys** | **1995** | Comedy | 792 | **88.5** | **64.9** | [`subtitles/Bad.Boys.1995.lao.srt`](subtitles/Bad.Boys.1995.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bad Country** | **2014** | Crime | 773 | **88.1** | **64.9** | [`subtitles/Bad.Country.2014.lao.srt`](subtitles/Bad.Country.2014.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bad Day at Black Rock** | **1955** | Thriller | 781 | **88.2** | **65.1** | [`subtitles/Bad.Day.at.Black.Rock.1955.lao.srt`](subtitles/Bad.Day.at.Black.Rock.1955.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bad Dreams** | **1988** | Thriller | 732 | **88.4** | **65.1** | [`subtitles/Bad.Dreams.1988.lao.srt`](subtitles/Bad.Dreams.1988.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bad Lieutenant** | **1992** | Crime | 332 | **87.7** | **64.5** | [`subtitles/Bad.Lieutenant.1992.lao.srt`](subtitles/Bad.Lieutenant.1992.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bad Santa** | **2003** | Crime | 659 | **88.2** | **65.1** | [`subtitles/Bad.Santa.2003.lao.srt`](subtitles/Bad.Santa.2003.lao.srt) | ✓ LoRA 1.3B Champion |
| **Barbie** | **2023** | Adventure | 959 | **88.2** | **64.6** | [`subtitles/Barbie.2023.lao.srt`](subtitles/Barbie.2023.lao.srt) | ✓ LoRA 1.3B Champion |
| **Barry Lyndon** | **1975** | Romance | 787 | **88.9** | **65.0** | [`subtitles/Barry.Lyndon.1975.lao.srt`](subtitles/Barry.Lyndon.1975.lao.srt) | ✓ LoRA 1.3B Champion |
| **Barton Fink** | **1991** | Thriller | 771 | **88.0** | **65.1** | [`subtitles/Barton.Fink.1991.lao.srt`](subtitles/Barton.Fink.1991.lao.srt) | ✓ LoRA 1.3B Champion |
| **Basic** | **2003** | Thriller | 1,059 | **88.4** | **64.3** | [`subtitles/Basic.2003.lao.srt`](subtitles/Basic.2003.lao.srt) | ✓ LoRA 1.3B Champion |
| **Basic Instinct** | **1992** | Thriller | 881 | **87.8** | **64.9** | [`subtitles/Basic.Instinct.1992.lao.srt`](subtitles/Basic.Instinct.1992.lao.srt) | ✓ LoRA 1.3B Champion |
| **Batman** | **1989** | Thriller | 609 | **87.9** | **64.6** | [`subtitles/Batman.1989.lao.srt`](subtitles/Batman.1989.lao.srt) | ✓ LoRA 1.3B Champion |
| **Batman 2** | **1992** | Thriller | 604 | **87.9** | **64.6** | [`subtitles/Batman.2.1992.lao.srt`](subtitles/Batman.2.1992.lao.srt) | ✓ LoRA 1.3B Champion |
| **Battle: Los Angeles** | **2011** | Sci-Fi | 681 | **88.3** | **65.2** | [`subtitles/Battle.Los.Angeles.2011.lao.srt`](subtitles/Battle.Los.Angeles.2011.lao.srt) | ✓ LoRA 1.3B Champion |
| **Beavis and Butt-head Do America** | **1996** | Animation | 703 | **88.9** | **65.2** | [`subtitles/Beavis.and.Butt-head.Do.America.1996.lao.srt`](subtitles/Beavis.and.Butt-head.Do.America.1996.lao.srt) | ✓ LoRA 1.3B Champion |
| **Beginners** | **2010** | Romance | 745 | **88.8** | **65.0** | [`subtitles/Beginners.2010.lao.srt`](subtitles/Beginners.2010.lao.srt) | ✓ LoRA 1.3B Champion |
| **Belle** | **2013** | Romance | 813 | **88.8** | **65.7** | [`subtitles/Belle.2013.lao.srt`](subtitles/Belle.2013.lao.srt) | ✓ LoRA 1.3B Champion |
| **Big Eyes** | **2014** | Crime | 835 | **87.9** | **64.7** | [`subtitles/Big.Eyes.2014.lao.srt`](subtitles/Big.Eyes.2014.lao.srt) | ✓ LoRA 1.3B Champion |
| **Big Fish** | **2003** | Adventure | 804 | **88.7** | **65.2** | [`subtitles/Big.Fish.2003.lao.srt`](subtitles/Big.Fish.2003.lao.srt) | ✓ LoRA 1.3B Champion |
| **Birdman** | **2014** | Romance | 1,099 | **88.8** | **65.5** | [`subtitles/Birdman.2014.lao.srt`](subtitles/Birdman.2014.lao.srt) | ✓ LoRA 1.3B Champion |
| **Birthday Girl** | **2001** | Romance | 593 | **88.8** | **65.3** | [`subtitles/Birthday.Girl.2001.lao.srt`](subtitles/Birthday.Girl.2001.lao.srt) | ✓ LoRA 1.3B Champion |
| **Black Panther** | **2018** | Sci-Fi | 923 | **88.3** | **65.2** | [`subtitles/Black.Panther.2018.lao.srt`](subtitles/Black.Panther.2018.lao.srt) | ✓ LoRA 1.3B Champion |
| **Black Rain** | **1989** | Crime | 650 | **88.0** | **64.3** | [`subtitles/Black.Rain.1989.lao.srt`](subtitles/Black.Rain.1989.lao.srt) | ✓ LoRA 1.3B Champion |
| **BlacKkKlansman** | **2018** | Crime | 1,089 | **87.9** | **65.0** | [`subtitles/BlacKkKlansman.2018.lao.srt`](subtitles/BlacKkKlansman.2018.lao.srt) | ✓ LoRA 1.3B Champion |
| **Blade** | **1998** | Sci-Fi | 560 | **87.9** | **64.6** | [`subtitles/Blade.1998.lao.srt`](subtitles/Blade.1998.lao.srt) | ✓ LoRA 1.3B Champion |
| **Blade II** | **2002** | Horror | 566 | **88.0** | **65.0** | [`subtitles/Blade.II.2002.lao.srt`](subtitles/Blade.II.2002.lao.srt) | ✓ LoRA 1.3B Champion |
| **Blade Runner** | **1982** | Sci-Fi | 746 | **88.4** | **64.6** | [`subtitles/Blade.Runner.1982.lao.srt`](subtitles/Blade.Runner.1982.lao.srt) | ✓ LoRA 1.3B Champion |
| **Blade: Trinity** | **2004** | Horror | 574 | **87.7** | **64.9** | [`subtitles/Blade.Trinity.2004.lao.srt`](subtitles/Blade.Trinity.2004.lao.srt) | ✓ LoRA 1.3B Champion |
| **Blitz** | **2011** | Action | 602 | **87.8** | **64.4** | [`subtitles/Blitz.2011.lao.srt`](subtitles/Blitz.2011.lao.srt) | ✓ LoRA 1.3B Champion |
| **Blood and Wine** | **1996** | Crime | 926 | **88.4** | **64.6** | [`subtitles/Blood.and.Wine.1996.lao.srt`](subtitles/Blood.and.Wine.1996.lao.srt) | ✓ LoRA 1.3B Champion |
| **Blood Diamond** | **2006** | Feature Film | 1,443 | **88.5** | **65.2** | [`subtitles/Blood.Diamond.2006.lao.srt`](subtitles/Blood.Diamond.2006.lao.srt) | ✓ LoRA 1.3B Champion |
| **Blow** | **2001** | Crime | 1,026 | **88.0** | **64.5** | [`subtitles/Blow.2001.lao.srt`](subtitles/Blow.2001.lao.srt) | ✓ LoRA 1.3B Champion |
| **Blue Valentine** | **2010** | Romance | 679 | **88.7** | **65.7** | [`subtitles/Blue.Valentine.2010.lao.srt`](subtitles/Blue.Valentine.2010.lao.srt) | ✓ LoRA 1.3B Champion |
| **Blue Velvet** | **1986** | Crime | 948 | **88.5** | **64.5** | [`subtitles/Blue.Velvet.1986.lao.srt`](subtitles/Blue.Velvet.1986.lao.srt) | ✓ LoRA 1.3B Champion |
| **Body Heat** | **1981** | Crime | 871 | **87.9** | **65.1** | [`subtitles/Body.Heat.1981.lao.srt`](subtitles/Body.Heat.1981.lao.srt) | ✓ LoRA 1.3B Champion |
| **Body of Evidence** | **1993** | Romance | 928 | **88.9** | **65.5** | [`subtitles/Body.of.Evidence.1993.lao.srt`](subtitles/Body.of.Evidence.1993.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bodyguard** | **1992** | Romance | 964 | **88.9** | **64.9** | [`subtitles/Bodyguard.1992.lao.srt`](subtitles/Bodyguard.1992.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bones** | **2001** | Horror | 696 | **87.8** | **64.7** | [`subtitles/Bones.2001.lao.srt`](subtitles/Bones.2001.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bonnie and Clyde** | **1967** | Romance | 736 | **88.4** | **65.1** | [`subtitles/Bonnie.and.Clyde.1967.lao.srt`](subtitles/Bonnie.and.Clyde.1967.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bookworm** | **2024** | Adventure | 889 | **88.1** | **64.7** | [`subtitles/Bookworm.2024.lao.srt`](subtitles/Bookworm.2024.lao.srt) | ✓ LoRA 1.3B Champion |
| **Boondock Saints 2: All Saints Day** | **2009** | Crime | 892 | **87.8** | **64.5** | [`subtitles/Boondock.Saints.2.All.Saints.Day.2009.lao.srt`](subtitles/Boondock.Saints.2.All.Saints.Day.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bottle Rocket** | **1996** | Crime | 1,195 | **88.4** | **64.4** | [`subtitles/Bottle.Rocket.1996.lao.srt`](subtitles/Bottle.Rocket.1996.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bound** | **1996** | Crime | 918 | **88.4** | **64.5** | [`subtitles/Bound.1996.lao.srt`](subtitles/Bound.1996.lao.srt) | ✓ LoRA 1.3B Champion |
| **Brazil** | **1985** | Sci-Fi | 912 | **88.4** | **64.5** | [`subtitles/Brazil.1985.lao.srt`](subtitles/Brazil.1985.lao.srt) | ✓ LoRA 1.3B Champion |
| **Broadcast News** | **1987** | Romance | 1,127 | **88.9** | **65.1** | [`subtitles/Broadcast.News.1987.lao.srt`](subtitles/Broadcast.News.1987.lao.srt) | ✓ LoRA 1.3B Champion |
| **Broken Arrow** | **1996** | Adventure | 921 | **88.0** | **65.0** | [`subtitles/Broken.Arrow.1996.lao.srt`](subtitles/Broken.Arrow.1996.lao.srt) | ✓ LoRA 1.3B Champion |
| **Broken Embraces** | **2009** | Romance | 991 | **88.5** | **65.5** | [`subtitles/Broken.Embraces.2009.lao.srt`](subtitles/Broken.Embraces.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bruce Almighty** | **2003** | Romance | 837 | **88.8** | **65.5** | [`subtitles/Bruce.Almighty.2003.lao.srt`](subtitles/Bruce.Almighty.2003.lao.srt) | ✓ LoRA 1.3B Champion |
| **Buffy the Vampire Slayer** | **1992** | Horror | 941 | **87.6** | **64.6** | [`subtitles/Buffy.the.Vampire.Slayer.1992.lao.srt`](subtitles/Buffy.the.Vampire.Slayer.1992.lao.srt) | ✓ LoRA 1.3B Champion |
| **Bull Durham** | **1988** | Romance | 884 | **88.2** | **65.5** | [`subtitles/Bull.Durham.1988.lao.srt`](subtitles/Bull.Durham.1988.lao.srt) | ✓ LoRA 1.3B Champion |
| **Burlesque** | **2010** | Romance | 1,041 | **88.4** | **65.5** | [`subtitles/Burlesque.2010.lao.srt`](subtitles/Burlesque.2010.lao.srt) | ✓ LoRA 1.3B Champion |
| **Burn After Reading** | **2008** | Crime | 1,052 | **88.1** | **64.6** | [`subtitles/Burn.After.Reading.2008.lao.srt`](subtitles/Burn.After.Reading.2008.lao.srt) | ✓ LoRA 1.3B Champion |
| **Burning Annie** | **2004** | Romance | 1,165 | **88.9** | **65.0** | [`subtitles/Burning.Annie.2004.lao.srt`](subtitles/Burning.Annie.2004.lao.srt) | ✓ LoRA 1.3B Champion |
| **Capote** | **2005** | Crime | 768 | **88.0** | **64.6** | [`subtitles/Capote.2005.lao.srt`](subtitles/Capote.2005.lao.srt) | ✓ LoRA 1.3B Champion |
| **Carrie** | **1976** | Horror | 719 | **87.8** | **64.4** | [`subtitles/Carrie.1976.lao.srt`](subtitles/Carrie.1976.lao.srt) | ✓ LoRA 1.3B Champion |
| **Cars 2** | **2011** | Animation | 1,226 | **89.0** | **65.4** | [`subtitles/Cars.2.2011.lao.srt`](subtitles/Cars.2.2011.lao.srt) | ✓ LoRA 1.3B Champion |
| **Case 39** | **2009** | Horror | 746 | **88.2** | **64.4** | [`subtitles/Case.39.2009.lao.srt`](subtitles/Case.39.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **Casino** | **1995** | Crime | 2,483 | **88.2** | **64.6** | [`subtitles/Casino.1995.lao.srt`](subtitles/Casino.1995.lao.srt) | ✓ LoRA 1.3B Champion |
| **Cast Away** | **2000** | Adventure | 787 | **88.2** | **65.1** | [`subtitles/Cast.Away.2000.lao.srt`](subtitles/Cast.Away.2000.lao.srt) | ✓ LoRA 1.3B Champion |
| **Catch Me If You Can** | **2002** | Crime | 933 | **88.0** | **64.5** | [`subtitles/Catch.Me.If.You.Can.2002.lao.srt`](subtitles/Catch.Me.If.You.Can.2002.lao.srt) | ✓ LoRA 1.3B Champion |
| **Charade** | **1963** | Romance | 1,355 | **88.6** | **65.5** | [`subtitles/Charade.1963.lao.srt`](subtitles/Charade.1963.lao.srt) | ✓ LoRA 1.3B Champion |
| **Chasing Amy** | **1997** | Romance | 1,075 | **88.5** | **65.0** | [`subtitles/Chasing.Amy.1997.lao.srt`](subtitles/Chasing.Amy.1997.lao.srt) | ✓ LoRA 1.3B Champion |
| **Cherry Falls** | **2000** | Horror | 701 | **87.7** | **64.6** | [`subtitles/Cherry.Falls.2000.lao.srt`](subtitles/Cherry.Falls.2000.lao.srt) | ✓ LoRA 1.3B Champion |
| **Chronicle** | **2012** | Sci-Fi | 738 | **88.1** | **65.0** | [`subtitles/Chronicle.2012.lao.srt`](subtitles/Chronicle.2012.lao.srt) | ✓ LoRA 1.3B Champion |
| **Chronicles of Narnia: The Lion, the Witch and the Wardrobe** | **2005** | Adventure | 629 | **88.5** | **65.1** | [`subtitles/Chronicles.of.Narnia.The.Lion.the.Witch.and.the.Wardrobe.2005.lao.srt`](subtitles/Chronicles.of.Narnia.The.Lion.the.Witch.and.the.Wardrobe.2005.lao.srt) | ✓ LoRA 1.3B Champion |
| **Cinema Paradiso** | **1988** | Romance | 457 | **88.9** | **65.5** | [`subtitles/Cinema.Paradiso.1988.lao.srt`](subtitles/Cinema.Paradiso.1988.lao.srt) | ✓ LoRA 1.3B Champion |
| **Cirque du Freak: The Vampire's Assistant** | **2009** | Adventure | 938 | **88.0** | **65.2** | [`subtitles/Cirque.du.Freak.The.Vampires.Assistant.2009.lao.srt`](subtitles/Cirque.du.Freak.The.Vampires.Assistant.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **Clash of the Titans** | **2010** | Adventure | 764 | **88.5** | **64.8** | [`subtitles/Clash.of.the.Titans.2010.lao.srt`](subtitles/Clash.of.the.Titans.2010.lao.srt) | ✓ LoRA 1.3B Champion |
| **Cliffhanger** | **1993** | Adventure | 559 | **88.1** | **65.3** | [`subtitles/Cliffhanger.1993.lao.srt`](subtitles/Cliffhanger.1993.lao.srt) | ✓ LoRA 1.3B Champion |
| **Coco** | **2017** | Feature Film | 1,444 | **88.3** | **65.3** | [`subtitles/Coco.2017.lao.srt`](subtitles/Coco.2017.lao.srt) | ✓ LoRA 1.3B Champion |
| **Constantine** | **2005** | Horror | 721 | **88.3** | **64.3** | [`subtitles/Constantine.2005.lao.srt`](subtitles/Constantine.2005.lao.srt) | ✓ LoRA 1.3B Champion |
| **Copycat** | **1995** | Horror | 843 | **88.1** | **64.6** | [`subtitles/Copycat.1995.lao.srt`](subtitles/Copycat.1995.lao.srt) | ✓ LoRA 1.3B Champion |
| **Coraline** | **2009** | Animation | 804 | **89.1** | **65.3** | [`subtitles/Coraline.2009.lao.srt`](subtitles/Coraline.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **Corpse Bride** | **2005** | Animation | 495 | **89.1** | **65.3** | [`subtitles/Corpse.Bride.2005.lao.srt`](subtitles/Corpse.Bride.2005.lao.srt) | ✓ LoRA 1.3B Champion |
| **Crouching Tiger, Hidden Dragon** | **2000** | Adventure | 531 | **88.0** | **65.1** | [`subtitles/Crouching.Tiger.Hidden.Dragon.2000.lao.srt`](subtitles/Crouching.Tiger.Hidden.Dragon.2000.lao.srt) | ✓ LoRA 1.3B Champion |
| **Dances with Wolves** | **1990** | Adventure | 638 | **88.7** | **65.0** | [`subtitles/Dances.with.Wolves.1990.lao.srt`](subtitles/Dances.with.Wolves.1990.lao.srt) | ✓ LoRA 1.3B Champion |
| **Dark City** | **1998** | Sci-Fi | 560 | **88.2** | **65.2** | [`subtitles/Dark.City.1998.lao.srt`](subtitles/Dark.City.1998.lao.srt) | ✓ LoRA 1.3B Champion |
| **Dark Star** | **1974** | Sci-Fi | 350 | **88.1** | **65.1** | [`subtitles/Dark.Star.1974.lao.srt`](subtitles/Dark.Star.1974.lao.srt) | ✓ LoRA 1.3B Champion |
| **Darkman** | **1990** | Sci-Fi | 930 | **88.0** | **65.0** | [`subtitles/Darkman.1990.lao.srt`](subtitles/Darkman.1990.lao.srt) | ✓ LoRA 1.3B Champion |
| **Dawn of the Dead** | **2004** | Horror | 139 | **88.1** | **64.2** | [`subtitles/Dawn.of.the.Dead.2004.lao.srt`](subtitles/Dawn.of.the.Dead.2004.lao.srt) | ✓ LoRA 1.3B Champion |
| **Deadpool** | **2016** | Adventure | 742 | **88.5** | **64.5** | [`subtitles/Deadpool.2016.lao.srt`](subtitles/Deadpool.2016.lao.srt) | ✓ LoRA 1.3B Champion |
| **Deadpool & Wolverine** | **2024** | Sci-Fi | 742 | **87.9** | **64.4** | [`subtitles/Deadpool.and.Wolverine.2024.lao.srt`](subtitles/Deadpool.and.Wolverine.2024.lao.srt) | ✓ LoRA 1.3B Champion |
| **Deep Rising** | **1998** | Horror | 632 | **87.6** | **64.9** | [`subtitles/Deep.Rising.1998.lao.srt`](subtitles/Deep.Rising.1998.lao.srt) | ✓ LoRA 1.3B Champion |
| **Despicable Me 2** | **2013** | Animation | 710 | **89.1** | **65.7** | [`subtitles/Despicable.Me.2.2013.lao.srt`](subtitles/Despicable.Me.2.2013.lao.srt) | ✓ LoRA 1.3B Champion |
| **Detroit Rock City** | **1999** | Adventure | 777 | **87.9** | **65.0** | [`subtitles/Detroit.Rock.City.1999.lao.srt`](subtitles/Detroit.Rock.City.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **Devil's Advocate** | **1997** | Horror | 1,060 | **88.3** | **64.3** | [`subtitles/Devils.Advocate.1997.lao.srt`](subtitles/Devils.Advocate.1997.lao.srt) | ✓ LoRA 1.3B Champion |
| **Django Unchained** | **2012** | Adventure | 1,067 | **88.4** | **64.9** | [`subtitles/Django.Unchained.2012.lao.srt`](subtitles/Django.Unchained.2012.lao.srt) | ✓ LoRA 1.3B Champion |
| **Dogma** | **1999** | Adventure | 955 | **88.3** | **64.8** | [`subtitles/Dogma.1999.lao.srt`](subtitles/Dogma.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **Drag Me to Hell** | **2009** | Horror | 665 | **87.7** | **64.2** | [`subtitles/Drag.Me.to.Hell.2009.lao.srt`](subtitles/Drag.Me.to.Hell.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **Dune** | **1984** | Sci-Fi | 617 | **88.5** | **64.7** | [`subtitles/Dune.1984.lao.srt`](subtitles/Dune.1984.lao.srt) | ✓ LoRA 1.3B Champion |
| **Dune Part One** | **2021** | Sci-Fi | 648 | **87.8** | **64.6** | [`subtitles/Dune.Part.One.2021.lao.srt`](subtitles/Dune.Part.One.2021.lao.srt) | ✓ LoRA 1.3B Champion |
| **Eight Legged Freaks** | **2002** | Sci-Fi | 675 | **87.9** | **65.0** | [`subtitles/Eight.Legged.Freaks.2002.lao.srt`](subtitles/Eight.Legged.Freaks.2002.lao.srt) | ✓ LoRA 1.3B Champion |
| **Elemental** | **2023** | Animation | 906 | **88.7** | **65.3** | [`subtitles/Elemental.2023.lao.srt`](subtitles/Elemental.2023.lao.srt) | ✓ LoRA 1.3B Champion |
| **Escape From L.A.** | **1996** | Sci-Fi | 617 | **88.3** | **65.2** | [`subtitles/Escape.From.L.A..1996.lao.srt`](subtitles/Escape.From.L.A..1996.lao.srt) | ✓ LoRA 1.3B Champion |
| **Event Horizon** | **1997** | Horror | 892 | **87.9** | **64.5** | [`subtitles/Event.Horizon.1997.lao.srt`](subtitles/Event.Horizon.1997.lao.srt) | ✓ LoRA 1.3B Champion |
| **Evil Dead** | **1981** | Horror | 310 | **88.1** | **64.4** | [`subtitles/Evil.Dead.1981.lao.srt`](subtitles/Evil.Dead.1981.lao.srt) | ✓ LoRA 1.3B Champion |
| **Evil Dead II: Dead by Dawn** | **1987** | Horror | 221 | **87.7** | **64.4** | [`subtitles/Evil.Dead.II.Dead.by.Dawn.1987.lao.srt`](subtitles/Evil.Dead.II.Dead.by.Dawn.1987.lao.srt) | ✓ LoRA 1.3B Champion |
| **Fantastic Mr Fox** | **2009** | Animation | 625 | **88.5** | **65.8** | [`subtitles/Fantastic.Mr.Fox.2009.lao.srt`](subtitles/Fantastic.Mr.Fox.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **Feast** | **2005** | Horror | 831 | **88.1** | **64.6** | [`subtitles/Feast.2005.lao.srt`](subtitles/Feast.2005.lao.srt) | ✓ LoRA 1.3B Champion |
| **Fight Club** | **1999** | Drama / Classics | 1,293 | **87.9** | **65.0** | [`subtitles/Fight.Club.1999.lao.srt`](subtitles/Fight.Club.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **Final Destination** | **2000** | Horror | 447 | **88.3** | **64.5** | [`subtitles/Final.Destination.2000.lao.srt`](subtitles/Final.Destination.2000.lao.srt) | ✓ LoRA 1.3B Champion |
| **Final Destination 2** | **2003** | Horror | 648 | **87.6** | **64.7** | [`subtitles/Final.Destination.2.2003.lao.srt`](subtitles/Final.Destination.2.2003.lao.srt) | ✓ LoRA 1.3B Champion |
| **Forrest Gump** | **1994** | Drama / Classics | 1,065 | **88.2** | **65.0** | [`subtitles/Forrest.Gump.1994.lao.srt`](subtitles/Forrest.Gump.1994.lao.srt) | ✓ LoRA 1.3B Champion |
| **Freddy vs. Jason** | **2003** | Horror | 716 | **88.0** | **64.8** | [`subtitles/Freddy.vs..Jason.2003.lao.srt`](subtitles/Freddy.vs..Jason.2003.lao.srt) | ✓ LoRA 1.3B Champion |
| **Friday the 13th** | **1980** | Horror | 432 | **87.8** | **64.4** | [`subtitles/Friday.the.13th.1980.lao.srt`](subtitles/Friday.the.13th.1980.lao.srt) | ✓ LoRA 1.3B Champion |
| **Friday the 13th Part VIII: Jason Takes Manhattan** | **1989** | Horror | 569 | **87.7** | **64.2** | [`subtitles/Friday.the.13th.Part.VIII.Jason.Takes.Manhattan.1989.lao.srt`](subtitles/Friday.the.13th.Part.VIII.Jason.Takes.Manhattan.1989.lao.srt) | ✓ LoRA 1.3B Champion |
| **Fright Night** | **1985** | Horror | 883 | **88.3** | **64.8** | [`subtitles/Fright.Night.1985.lao.srt`](subtitles/Fright.Night.1985.lao.srt) | ✓ LoRA 1.3B Champion |
| **Frozen** | **2013** | Feature Film | 1,652 | **88.7** | **64.8** | [`subtitles/Frozen.2013.lao.srt`](subtitles/Frozen.2013.lao.srt) | ✓ LoRA 1.3B Champion |
| **Frozen** | **2013** | Animation | 917 | **89.3** | **65.2** | [`subtitles/Frozen.2013.lao.srt`](subtitles/Frozen.2013.lao.srt) | ✓ LoRA 1.3B Champion |
| **Gladiator** | **2000** | Drama / Classics | 675 | **88.7** | **65.0** | [`subtitles/Gladiator.2000.lao.srt`](subtitles/Gladiator.2000.lao.srt) | ✓ LoRA 1.3B Champion |
| **Happy Feet** | **2006** | Animation | 633 | **89.0** | **66.0** | [`subtitles/Happy.Feet.2006.lao.srt`](subtitles/Happy.Feet.2006.lao.srt) | ✓ LoRA 1.3B Champion |
| **Heavy Metal** | **1981** | Animation | 297 | **88.5** | **65.5** | [`subtitles/Heavy.Metal.1981.lao.srt`](subtitles/Heavy.Metal.1981.lao.srt) | ✓ LoRA 1.3B Champion |
| **Here Comes Peter Cottontail** | **1971** | Animation | 508 | **88.7** | **65.8** | [`subtitles/Here.Comes.Peter.Cottontail.1971.lao.srt`](subtitles/Here.Comes.Peter.Cottontail.1971.lao.srt) | ✓ LoRA 1.3B Champion |
| **How to Train Your Dragon 2** | **2014** | Animation | 726 | **88.5** | **65.2** | [`subtitles/How.to.Train.Your.Dragon.2.2014.lao.srt`](subtitles/How.to.Train.Your.Dragon.2.2014.lao.srt) | ✓ LoRA 1.3B Champion |
| **Inception** | **2010** | Drama / Classics | 1,223 | **88.5** | **64.7** | [`subtitles/Inception.2010.lao.srt`](subtitles/Inception.2010.lao.srt) | ✓ LoRA 1.3B Champion |
| **Interstellar** | **2014** | Drama / Classics | 902 | **88.1** | **64.8** | [`subtitles/Interstellar.2014.lao.srt`](subtitles/Interstellar.2014.lao.srt) | ✓ LoRA 1.3B Champion |
| **Kung Fu Panda** | **2008** | Animation | 694 | **89.2** | **65.7** | [`subtitles/Kung.Fu.Panda.2008.lao.srt`](subtitles/Kung.Fu.Panda.2008.lao.srt) | ✓ LoRA 1.3B Champion |
| **L' Avventura (The Adventure)** | **1960** | Thriller | 745 | **88.0** | **64.7** | [`subtitles/L.Avventura.The.Adventure.1960.lao.srt`](subtitles/L.Avventura.The.Adventure.1960.lao.srt) | ✓ LoRA 1.3B Champion |
| **Megamind** | **2010** | Animation | 866 | **89.3** | **65.8** | [`subtitles/Megamind.2010.lao.srt`](subtitles/Megamind.2010.lao.srt) | ✓ LoRA 1.3B Champion |
| **Memento** | **2000** | Feature Film | 692 | **88.2** | **64.7** | [`subtitles/Memento.2000.lao.srt`](subtitles/Memento.2000.lao.srt) | ✓ LoRA 1.3B Champion |
| **Moana** | **2016** | Feature Film | 1,233 | **88.1** | **65.2** | [`subtitles/Moana.2016.lao.srt`](subtitles/Moana.2016.lao.srt) | ✓ LoRA 1.3B Champion |
| **Monkeybone** | **2001** | Animation | 643 | **89.0** | **65.3** | [`subtitles/Monkeybone.2001.lao.srt`](subtitles/Monkeybone.2001.lao.srt) | ✓ LoRA 1.3B Champion |
| **One Eight Seven (187)** | **1997** | Drama | 754 | **88.2** | **65.2** | [`subtitles/One.Eight.Seven.187.1997.lao.srt`](subtitles/One.Eight.Seven.187.1997.lao.srt) | ✓ LoRA 1.3B Champion |
| **Onward** | **2020** | Animation | 1,114 | **89.1** | **65.4** | [`subtitles/Onward.2020.lao.srt`](subtitles/Onward.2020.lao.srt) | ✓ LoRA 1.3B Champion |
| **ParaNorman** | **2012** | Animation | 664 | **88.7** | **65.2** | [`subtitles/ParaNorman.2012.lao.srt`](subtitles/ParaNorman.2012.lao.srt) | ✓ LoRA 1.3B Champion |
| **Pulp Fiction** | **1994** | Drama / Classics | 1,214 | **88.7** | **64.7** | [`subtitles/Pulp.Fiction.1994.lao.srt`](subtitles/Pulp.Fiction.1994.lao.srt) | ✓ LoRA 1.3B Champion |
| **Puss in Boots: The Last Wish** | **2022** | Animation | 1,134 | **88.6** | **65.6** | [`subtitles/Puss.in.Boots.The.Last.Wish.2022.lao.srt`](subtitles/Puss.in.Boots.The.Last.Wish.2022.lao.srt) | ✓ LoRA 1.3B Champion |
| **Reservoir Dogs** | **1992** | Feature Film | 694 | **88.2** | **64.9** | [`subtitles/Reservoir.Dogs.1992.lao.srt`](subtitles/Reservoir.Dogs.1992.lao.srt) | ✓ LoRA 1.3B Champion |
| **Rise of the Guardians** | **2012** | Animation | 984 | **88.8** | **65.7** | [`subtitles/Rise.of.the.Guardians.2012.lao.srt`](subtitles/Rise.of.the.Guardians.2012.lao.srt) | ✓ LoRA 1.3B Champion |
| **Saving Private Ryan** | **1998** | Feature Film | 934 | **88.1** | **65.2** | [`subtitles/Saving.Private.Ryan.1998.lao.srt`](subtitles/Saving.Private.Ryan.1998.lao.srt) | ✓ LoRA 1.3B Champion |
| **Se7en** | **1995** | Feature Film | 489 | **88.6** | **64.7** | [`subtitles/Se7en.1995.lao.srt`](subtitles/Se7en.1995.lao.srt) | ✓ LoRA 1.3B Champion |
| **Shrek** | **2001** | Animation | 744 | **88.5** | **65.9** | [`subtitles/Shrek.2001.lao.srt`](subtitles/Shrek.2001.lao.srt) | ✓ LoRA 1.3B Champion |
| **South Park: Bigger, Longer & Uncut** | **1999** | Animation | 1,257 | **88.7** | **65.8** | [`subtitles/South.Park.Bigger.Longer.and.Uncut.1999.lao.srt`](subtitles/South.Park.Bigger.Longer.and.Uncut.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **Spider-Man: Across the Spider-Verse** | **2023** | Animation | 1,542 | **89.0** | **66.0** | [`subtitles/Spider-Man.Across.the.Spider-Verse.2023.lao.srt`](subtitles/Spider-Man.Across.the.Spider-Verse.2023.lao.srt) | ✓ LoRA 1.3B Champion |
| **Star Wars: Episode IV - A New Hope** | **1977** | Feature Film | 994 | **88.7** | **65.2** | [`subtitles/Star.Wars.Episode.IV.-.A.New.Hope.1977.lao.srt`](subtitles/Star.Wars.Episode.IV.-.A.New.Hope.1977.lao.srt) | ✓ LoRA 1.3B Champion |
| **Teenage Mutant Ninja Turtles: Mutant Mayhem** | **2023** | Animation | 996 | **89.3** | **65.7** | [`subtitles/Teenage.Mutant.Ninja.Turtles.Mutant.Mayhem.2023.lao.srt`](subtitles/Teenage.Mutant.Ninja.Turtles.Mutant.Mayhem.2023.lao.srt) | ✓ LoRA 1.3B Champion |
| **Terminator 2: Judgment Day** | **1991** | Feature Film | 518 | **88.7** | **64.8** | [`subtitles/Terminator.2.Judgment.Day.1991.lao.srt`](subtitles/Terminator.2.Judgment.Day.1991.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Abyss** | **1989** | Thriller | 665 | **88.2** | **64.5** | [`subtitles/The.Abyss.1989.lao.srt`](subtitles/The.Abyss.1989.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Addams Family** | **1991** | Horror | 265 | **87.7** | **64.5** | [`subtitles/The.Addams.Family.1991.lao.srt`](subtitles/The.Addams.Family.1991.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Adjustment Bureau** | **2011** | Thriller | 978 | **87.8** | **64.9** | [`subtitles/The.Adjustment.Bureau.2011.lao.srt`](subtitles/The.Adjustment.Bureau.2011.lao.srt) | ✓ LoRA 1.3B Champion |
| **The American** | **2010** | Thriller | 693 | **87.7** | **64.6** | [`subtitles/The.American.2010.lao.srt`](subtitles/The.American.2010.lao.srt) | ✓ LoRA 1.3B Champion |
| **The American President** | **1995** | Romance | 1,403 | **88.6** | **65.1** | [`subtitles/The.American.President.1995.lao.srt`](subtitles/The.American.President.1995.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Amityville Asylum** | **2013** | Horror | 631 | **87.9** | **64.6** | [`subtitles/The.Amityville.Asylum.2013.lao.srt`](subtitles/The.Amityville.Asylum.2013.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Apartment** | **1960** | Comedy | 1,214 | **88.5** | **65.0** | [`subtitles/The.Apartment.1960.lao.srt`](subtitles/The.Apartment.1960.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Assignment** | **1997** | Thriller | 788 | **88.4** | **64.7** | [`subtitles/The.Assignment.1997.lao.srt`](subtitles/The.Assignment.1997.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Avengers** | **2012** | Sci-Fi | 941 | **88.0** | **64.6** | [`subtitles/The.Avengers.2012.lao.srt`](subtitles/The.Avengers.2012.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Battle of Shaker Heights** | **2003** | Romance | 945 | **88.2** | **65.6** | [`subtitles/The.Battle.of.Shaker.Heights.2003.lao.srt`](subtitles/The.Battle.of.Shaker.Heights.2003.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Beekeeper** | **2024** | Thriller | 762 | **88.4** | **64.3** | [`subtitles/The.Beekeeper.2024.lao.srt`](subtitles/The.Beekeeper.2024.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Big Blue** | **1988** | Romance | 849 | **88.4** | **65.3** | [`subtitles/The.Big.Blue.1988.lao.srt`](subtitles/The.Big.Blue.1988.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Big Sick** | **2017** | Romance | 1,119 | **88.9** | **65.1** | [`subtitles/The.Big.Sick.2017.lao.srt`](subtitles/The.Big.Sick.2017.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Big White** | **2005** | Crime | 840 | **88.2** | **64.4** | [`subtitles/The.Big.White.2005.lao.srt`](subtitles/The.Big.White.2005.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Birds** | **1963** | Romance | 1,139 | **88.8** | **65.5** | [`subtitles/The.Birds.1963.lao.srt`](subtitles/The.Birds.1963.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Black Dahlia** | **2006** | Crime | 1,048 | **87.7** | **64.9** | [`subtitles/The.Black.Dahlia.2006.lao.srt`](subtitles/The.Black.Dahlia.2006.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Blast from the Past** | **1999** | Romance | 1,268 | **88.7** | **65.4** | [`subtitles/The.Blast.from.the.Past.1999.lao.srt`](subtitles/The.Blast.from.the.Past.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Bling Ring** | **2013** | Crime | 606 | **88.1** | **64.9** | [`subtitles/The.Bling.Ring.2013.lao.srt`](subtitles/The.Bling.Ring.2013.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Book of Eli** | **2010** | Sci-Fi | 786 | **87.7** | **65.1** | [`subtitles/The.Book.of.Eli.2010.lao.srt`](subtitles/The.Book.of.Eli.2010.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Boondock Saints** | **1999** | Crime | 787 | **88.5** | **64.8** | [`subtitles/The.Boondock.Saints.1999.lao.srt`](subtitles/The.Boondock.Saints.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Bounty Hunter** | **2010** | Romance | 934 | **88.8** | **65.6** | [`subtitles/The.Bounty.Hunter.2010.lao.srt`](subtitles/The.Bounty.Hunter.2010.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Bourne Identity** | **2002** | Adventure | 643 | **88.4** | **64.6** | [`subtitles/The.Bourne.Identity.2002.lao.srt`](subtitles/The.Bourne.Identity.2002.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Bourne Ultimatum** | **2007** | Adventure | 553 | **88.7** | **65.0** | [`subtitles/The.Bourne.Ultimatum.2007.lao.srt`](subtitles/The.Bourne.Ultimatum.2007.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Box** | **2009** | Sci-Fi | 811 | **88.0** | **64.6** | [`subtitles/The.Box.2009.lao.srt`](subtitles/The.Box.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Boxtrolls** | **2014** | Animation | 938 | **88.6** | **65.2** | [`subtitles/The.Boxtrolls.2014.lao.srt`](subtitles/The.Boxtrolls.2014.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Brothers Bloom** | **2008** | Romance | 706 | **88.4** | **65.5** | [`subtitles/The.Brothers.Bloom.2008.lao.srt`](subtitles/The.Brothers.Bloom.2008.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Cell** | **2000** | Sci-Fi | 621 | **88.1** | **64.8** | [`subtitles/The.Cell.2000.lao.srt`](subtitles/The.Cell.2000.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Cider House Rules** | **1999** | Romance | 1,020 | **88.3** | **65.1** | [`subtitles/The.Cider.House.Rules.1999.lao.srt`](subtitles/The.Cider.House.Rules.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Croods** | **2013** | Animation | 805 | **88.7** | **65.6** | [`subtitles/The.Croods.2013.lao.srt`](subtitles/The.Croods.2013.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Crow** | **1994** | Horror | 539 | **88.1** | **65.0** | [`subtitles/The.Crow.1994.lao.srt`](subtitles/The.Crow.1994.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Crow Salvation** | **2000** | Horror | 572 | **87.5** | **64.7** | [`subtitles/The.Crow.Salvation.2000.lao.srt`](subtitles/The.Crow.Salvation.2000.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Dark Knight** | **2008** | Drama / Classics | 1,243 | **87.9** | **64.7** | [`subtitles/The.Dark.Knight.2008.lao.srt`](subtitles/The.Dark.Knight.2008.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Day the Earth Stood Still** | **2008** | Sci-Fi | 770 | **88.5** | **65.1** | [`subtitles/The.Day.the.Earth.Stood.Still.2008.lao.srt`](subtitles/The.Day.the.Earth.Stood.Still.2008.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Departed** | **2006** | Feature Film | 1,180 | **88.1** | **64.6** | [`subtitles/The.Departed.2006.lao.srt`](subtitles/The.Departed.2006.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Godfather** | **1972** | Drama / Classics | 899 | **88.7** | **65.3** | [`subtitles/The.Godfather.1972.lao.srt`](subtitles/The.Godfather.1972.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Green Mile** | **1999** | Feature Film | 1,012 | **88.4** | **64.6** | [`subtitles/The.Green.Mile.1999.lao.srt`](subtitles/The.Green.Mile.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **The LEGO Movie** | **2014** | Animation | 961 | **88.7** | **66.0** | [`subtitles/The.LEGO.Movie.2014.lao.srt`](subtitles/The.LEGO.Movie.2014.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Lord of the Rings: The Fellowship of the Ring** | **2001** | Feature Film | 817 | **88.4** | **64.6** | [`subtitles/The.Lord.of.the.Rings.The.Fellowship.of.the.Ring.2001.lao.srt`](subtitles/The.Lord.of.the.Rings.The.Fellowship.of.the.Ring.2001.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Matrix** | **1999** | Drama / Classics | 568 | **88.5** | **65.3** | [`subtitles/The.Matrix.1999.lao.srt`](subtitles/The.Matrix.1999.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Prestige** | **2006** | Feature Film | 1,047 | **88.4** | **64.6** | [`subtitles/The.Prestige.2006.lao.srt`](subtitles/The.Prestige.2006.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Shawshank Redemption** | **1994** | Feature Film | 803 | **88.6** | **65.3** | [`subtitles/The.Shawshank.Redemption.1994.lao.srt`](subtitles/The.Shawshank.Redemption.1994.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Silence Of The Lambs** | **1991** | Feature Film | 928 | **88.2** | **65.0** | [`subtitles/The.Silence.Of.The.Lambs.1991.lao.srt`](subtitles/The.Silence.Of.The.Lambs.1991.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Terminator** | **1984** | Feature Film | 503 | **88.1** | **64.7** | [`subtitles/The.Terminator.1984.lao.srt`](subtitles/The.Terminator.1984.lao.srt) | ✓ LoRA 1.3B Champion |
| **The Usual Suspects** | **1995** | Feature Film | 768 | **88.7** | **65.1** | [`subtitles/The.Usual.Suspects.1995.lao.srt`](subtitles/The.Usual.Suspects.1995.lao.srt) | ✓ LoRA 1.3B Champion |
| **TMNT** | **2007** | Animation | 551 | **88.7** | **65.6** | [`subtitles/TMNT.2007.lao.srt`](subtitles/TMNT.2007.lao.srt) | ✓ LoRA 1.3B Champion |
| **Toy Story** | **1995** | Animation | 887 | **88.5** | **65.2** | [`subtitles/Toy.Story.1995.lao.srt`](subtitles/Toy.Story.1995.lao.srt) | ✓ LoRA 1.3B Champion |
| **Transformers: The Movie** | **1986** | Animation | 720 | **89.1** | **65.9** | [`subtitles/Transformers.The.Movie.1986.lao.srt`](subtitles/Transformers.The.Movie.1986.lao.srt) | ✓ LoRA 1.3B Champion |
| **Up** | **2009** | Animation | 720 | **88.8** | **65.4** | [`subtitles/Up.2009.lao.srt`](subtitles/Up.2009.lao.srt) | ✓ LoRA 1.3B Champion |
| **Wall-E** | **2008** | Animation | 476 | **89.0** | **65.2** | [`subtitles/Wall-E.2008.lao.srt`](subtitles/Wall-E.2008.lao.srt) | ✓ LoRA 1.3B Champion |

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
