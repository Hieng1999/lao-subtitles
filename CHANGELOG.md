# Changelog

## 2026-09-22

Catalog refresh with adapter `night7_S3X_e2` (stage 1), pending reader check. This entry
records the honesty changes made in preparation, ahead of the actual subtitle refresh (which
is gated on the reader's verdict and has not happened yet):

- Every "Verified" / "Back-Translation Verified" badge on the site and in this README now
  reads "Machine translation, not reviewed by a person."
- Per-film round-trip / chrF++ / BLEU numbers removed from movie cards and the README table.
- A site-wide notice near the top of the index page and this README: translated by a local
  machine-translation model, no human review, errors and stiff phrasing are expected, how to
  report a bad line -- with an empty slot for a Lao version of the same notice, to be filled
  in by a Lao-reading reviewer, not composed by the agent.
- A "Report a bad line" link on every movie card, opening a pre-filled GitHub issue.
- Per-film stats changed to: model version label, last-updated date, line count, and an
  automatic defect check count (flagged/total) -- replacing the removed "Verified: N fixed"
  and round-trip figures, which could not be honestly recomputed from local data alone.
