# Changelog

## 2026-09-29 (catalog update)

Catalog update (batch 3): 797 films, up from 551. 610 of them are now real "Subtitles"
files (was 303) and 187 are still "Translated screenplay" files (was 248).

- **246 new films.** Their English subtitles came from an English subtitle track already
  inside the film file, rather than from a separate download. 241 are new films. The
  other 5 are cards for a particular cut of a film: Avatar (Extended) and Blade: Trinity
  (Unrated) are a second card beside the film's existing card, while Battle Royale,
  Kingdom of Heaven and Pitch Black are listed only as their Director's Cut -- there is
  no separate card for the theatrical version of those three.
- **61 "Translated screenplay" cards became "Subtitles" cards.** Those films now have a
  Lao file timed to the film's real dialogue instead of a screenplay with even spacing.
- **Venom is listed as a 2018 film.** It was listed as 2019, which is wrong: Venom was
  released in 2018. Its card and both of its files moved from `Venom.2019` to
  `Venom.2018`.
- **Attribution lines now have to name subtitle work.** A credit carried out of an
  English subtitle file is only shown when it says it is about the subtitles --
  subtitles, captions, transcription, syncing, correction, translation or dialogue. A
  credit naming something else (for example a video re-encoder and a release group) is
  not a subtitle source, so those cards say "English subtitle source not stated"
  instead. Measured against the site as it stood before this update: 12 cards that were
  already listed now show a different line -- 6 say the English subtitle source is not
  stated, 3 show a name that had been cut off before, and 3 lost a trailing "-" or "~"
  that was part of the credit's decoration. The 61 cards that changed from "Translated
  screenplay" to "Subtitles" gain an attribution line, which they did not have at all.
- **Three titles corrected:** "Alien Verses Predator" -> "Alien vs. Predator", "Alien
  Verses Predator Requiem" -> "Alien vs. Predator Requiem", and "The Hitmans Wifes
  Bodyguard" -> "The Hitman's Wife's Bodyguard".
- **Six duplicate or broken cards removed.** "Hobbs & Shaw" and "Fast & Furious
  Presents: Hobbs & Shaw" were the same film and are now one card; "Cowboys & Aliens",
  "Tom & Jerry" and "Victoria & Abdul" moved to file names that spell out "and"; and the
  Batman v Superman Ultimate Edition card, whose file name ended in a stray ".None",
  became a theatrical card plus a proper Ultimate Edition card.
- **The README and the website text were corrected.** Claims that no step of this
  project actually checks were removed: that these films have no Lao subtitles anywhere
  else, that the Lao reads naturally, that every film in the catalogue was re-checked
  line by line against its English source, that the timing is aligned to the film's
  audio, and a set of case studies explaining what Lao words mean. Every verification
  number now says which films it counts and which file it was counted from; the film
  tables show each film's type and, where there is one, its edition; and the "How to
  Use" steps name the real download buttons and say what the timing of each kind of file
  actually is.
- **11 films are held back** and keep whatever card they already had: 8 whose title could
  not be resolved, Beauty and the Beast (2017) and Asteroid City (2023), which did not
  pass the automatic checks, and the theatrical cut of Avatar (2009), which has not been
  translated yet.

## 2026-09-26 (catalog update)

Catalog update (Part S2): fixes found by re-checking the live batch-1 site (555 films,
published earlier the same day) plus a second publish batch.

- **Duplicate cards fixed.** Catalog<->library re-matching now strips edition words
  (Special Edition, Director's Cut, Unrated, Assembly Cut, Remastered, Theatrical,
  Ultimate Edition, Final Cut) and folds "verses"/"vs." together before comparing
  titles. Found 4 films that were published twice -- once as an old "Translated
  screenplay" catalog card, once as a separate "Subtitles" library card missing only
  because of an edition word or an extra series-name prefix: Alien (1979, "Directors
  Cut"), Alien 3 (1992, "Assembly Cut"), Aliens (1986, "Special Edition"), and The Dark
  Knight (2008, from a folder named "Batman The Dark Knight"). Each now has one card,
  under its catalog stem, showing the cut it's actually timed to. A genuinely different
  cut of an already-sourced catalog film, or two library folders for different editions
  of the same film, still get separate cards. Two folders found to be true duplicates
  (same film, same cut) publish the one with more kept lines and drop the other
  (Batman V Superman: Dawn of Justice).
- **Library titles corrected.** Rebuilt library metadata from fresh OpenSubtitles
  searches with a stricter accept rule (year must match; title must match exactly, or
  the search result's words must all appear in the folder's own words, or word-overlap
  (Jaccard) >= 0.8) -- rejects a same-word-count coincidence, so a folder named
  "Robin Hood" no longer canonicalizes to the unrelated film "Christopher Robin" (this
  library's most visible past mismatch); 13 titles corrected this run (e.g. "Batman The
  Dark Knight Rises" -> "The Dark Knight Rises"), the rest kept their cleaned folder name
  when no confident search match existed. Never carries over an id from the old,
  unreliable metadata file. Also fixed 4 titles that were showing a raw "&amp;" instead
  of "&" (OpenSubtitles' own title field carries HTML entities verbatim).
- **A privacy leak in one attribution line fixed.** Alita: Battle Angel's credit line was
  showing the uploader's donation message and personal phone number, because the credit
  text's own line breaks were being erased before the code looked for a stopping point.
  Every attribution is now built one physical line at a time; a line break always ends
  it. Scanned every published attribution afterward for donation/ad/phone-number
  patterns: none found.
- **"How We Verify Quality" card scoped correctly.** Its numbers (automatic re-
  translation and pattern-check corrections) have only ever described the older
  "Translated screenplay" files; the card now says so explicitly, drops the
  "Independently" claim, and adds a plain line for "Subtitles" files stating what is
  actually checked for them (model weights, per-line timing, non-empty lines, credit/ad
  removal, defect-pattern checks) and that no quality score is published for them yet.
- **One unit on every card.** "Subtitles" cards now say "N lines", matching "Translated
  screenplay" cards (was "N cues").
- Toy Story 4 (2019), held back from batch 1 over a false timing-check failure (two
  English cues sharing one timestamp), is now published -- the check is a multiset
  comparison, so a shared timestamp on the English side no longer fails a Lao file whose
  own cues all genuinely match.
- Verified: link check 0 failures; every listed film's site files byte-identical to the
  translated source; subtitle/screenplay counts match the page header; 0 local paths; 0
  attributions with a 6+ digit run or a donation/ad-boilerplate word; 0 duplicate
  title+year+cut on the page; headless Chrome confirms card count, both labels, 0 "n/a".

## 2026-09-26

Catalog rebuild: published the S3X-translated R2 batch (Part S1), the adapter staged as
"pending reader check" in the 2026-09-22 entry below. Publishes now, on the pre-registered
default (S3X, chosen before any reader data existed -- no reader has reviewed it yet).

- 303 of 304 R2-verified films published: 33 replace an existing "Translated screenplay"
  catalog entry in place (same site file name, same card), 270 are brand-new library
  additions. 1 film held back and not added (Toy Story 4 (2019) -- a disclosed, non-blocking
  by-timing pairing collapse from the R2 verification, outside this rebuild's scope to fix).
  0 site-filename clashes.
- Both files published for every listed film: the real, timed Lao `.lao.srt` and the
  paired `.bilingual.srt`, copied byte-for-byte from the verified R2 output -- confirmed
  identical for all 303 films, never read from the older `.Lao.reviewed.srt` pipeline.
- Catalog: 555 movies total (was 285) -- 303 labeled "Subtitles · machine translation, not
  reviewed by a person" (independently confirmed by `tools/site/srt_kind.py`'s own
  classification, not just the label), 252 still "Translated screenplay · synthetic timing
  · not synced to the film", being replaced as real subtitle files arrive.
- Site-wide wording: the Gemini cloud-review disclosure is now scoped to "Translated
  screenplay" files only (S3X's pipeline has no review/patch step, cloud or otherwise). A
  new sentence describes S3X (NLLB-200 1.3B + LoRA adapter S3X, no cloud AI step, no
  find-and-replace rule tables) wherever the Gemini sentence appears. `docs/model_history.json`
  gets a new `s3x` generation entry (no score fields -- none has been measured).
- Attribution for the English source of every listed film, on its card: OpenSubtitles-API
  downloads read "English subtitles: `<uploader>` on OpenSubtitles", linked to the
  subtitle's page; everything else shows its own real credit line when the source file
  carried one (e.g. "Subtitles by SDl Media Group"), filtering out OpenSubtitles.org/YTS ad
  boilerplate that names no one; otherwise "English subtitle source not stated". Never a
  file path.
- Fixed a stale honesty leftover found while grepping the regenerated site for banned
  phrases: the Model Evolution card's "Real, Measured Progress" badge and "Every score
  shown here is a real, computed benchmark result" line were both wrong (every generation's
  score fields are `null` -- no score has ever been shown there); reworded to "No Quality
  Score Yet" / describes only the real counts (corrections applied, dataset rows staged).
- Fixed `tools/site/verify_site_links.py`'s link-collection regex: it matched any href
  containing the substring "/subtitles/", which coincidentally also matched the new
  OpenSubtitles.com attribution links (e.g. `.../en/subtitles/123-foo`) as if they were
  local file references. Anchored to this site's own `raw.githubusercontent.com` download
  URL prefix instead.
- Verified: `verify_site_links.py` 0 failures (1,110 hrefs = 2 x 555 cards); `srt_kind.py`
  counts (303 subtitle / 252 screenplay) match the page's own header counts; 0 local paths
  anywhere in the published site; headless Chrome against a local server (started and
  stopped in the same step) confirms 555 cards, both quality labels present, 0 "n/a".
- 608 files changed (540 added, 68 modified, 0 deleted); `subtitles/` is now 217 MB.

## 2026-09-22

Catalog refresh with adapter `night7_S3X_e2` (stage 1), pending reader check. This entry
records the honesty changes made in preparation, ahead of the actual subtitle refresh (which
is gated on the reader's verdict and has not happened yet).

**Correction (Part AH-1b):** an earlier version of this entry attributed the ~196 subtitle
files touched by the branch-prep commit to "the standing correction pipeline's ongoing
activity." That was wrong. Those files are the operator's 2026-09-15/16 revert of 127
hallucinated greetings across 99 films (Change 034), which had never been synced to this site
repo -- there is no ongoing correction pipeline separate from that one-time revert. Verified
mechanically: 132 distinct changed cues on the branch, all 132 matching the greeting token the
Change-034 revert removed, 0 unexplained.

Honesty changes:

- Every "Verified" / "Back-Translation Verified" badge now reads "Machine translation, not
  reviewed by a person."
- Per-film round-trip / chrF++ / BLEU numbers removed from movie cards and the README table.
- The site-wide notice near the top of the index page and this README (no human review,
  errors expected, how to report a line) only shows a Lao version when one has actually been
  supplied -- no placeholder/"pending" text ships when it hasn't.
- A "Report a bad line" link on every movie card, opening a pre-filled GitHub issue.
- Per-film stats: model version label, last-updated date, line count, automatic defect check
  (flagged/total) -- replacing "Verified: N fixed" and round-trip figures.
- The Model Evolution timeline's round-trip chrF++/BLEU block removed for the current
  generation; the generator no longer auto-rewrites it from stale benchmark data without an
  explicit operator flag.
