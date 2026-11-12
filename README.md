# OpenKAGE — Anonymous Result Records

This repository hosts the result records for an anonymous ICLR 2027 submission. The code-only supplementary ZIP is distributed separately on OpenReview; the full `results/` directory is provided here as one Release asset.

## Download and verify

Download `openkage_anonymous_results.tar.zst` from the Releases page. Its SHA-256 is listed in `SHA256SUMS.txt` and in the Release notes.

```bash
sha256sum -c SHA256SUMS.txt
tar --zstd -xf openkage_anonymous_results.tar.zst
```

Extract the archive next to the code-only supplementary package, so that `results/` is a sibling of `openkage/`, `experiments/`, `viewer/` and `paper/`. Then, from the code package root:

```bash
python experiments/paper_metrics.py --cell ds_openkage --summary
python experiments/plot_paper_progress.py
```

Neither command requires an LLM endpoint or a Minecraft server. Regenerating figures requires `matplotlib`, `Pillow` and Inkscape.

## Contents

- `manifest.tsv`: index of all 161 released runs.
- For each cell and run: flattened daily checkpoints, whitelisted run configuration, per-day context dumps, knowledge-graph databases, window snapshots and per-arm logs.
- Key-event footage frames and the milestone/item icons used by the figures and viewer.

World saves and vector-index sidecars are not included. The compressed archive is about 1.12 GiB and expands to about 5.56 GiB.

## Anonymity

These are anonymous review artifacts. Author names, host names, account names, internal paths and credentials were removed; model ids are normalized and no provider or endpoint tags are present. Some logged model outputs are in Chinese. Citation details and licensing will be provided after the review period.
