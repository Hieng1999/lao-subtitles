# Changelog

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
