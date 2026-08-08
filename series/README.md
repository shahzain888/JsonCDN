# Series CDN layout for MetflicPaywall

Upload this folder to your JsonCDN repo as `series/`:

```
series/
  catalog.json          # browse rows (genres → show cards)
  keywords.json         # search index (title + keywords, no episodes)
  batches/
    batch_000.json      # ~80 shows each, full seasons/episodes
    batch_001.json
    ...
  manifest.json
```

App loads:
1. **Series screen** → `catalog.json` only (~2.5 MB)
2. **Search** → `keywords.json` only (~1.5 MB) + movies feed
3. **Show click** → one `batches/batch_XXX.json` (~0.2–0.5 MB)

Regenerate from `NewPL_Seasons.json`:

```bash
py -3 batch_series.py
```
