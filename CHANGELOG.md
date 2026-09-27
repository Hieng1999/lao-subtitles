# Changelog

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
