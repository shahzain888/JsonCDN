# BWT videos CDN layout

Upload this folder to JsonCDN as `bwt_videos/`:

```
bwt_videos/
  keywords.json     # search index (title + url + thumbnail) — app loads this
  manifest.json
  batches/
    batch_000.json
    ...
```

App search flow:
1. Load `keywords.json` once (CDN)
2. Filter by user query on title/keywords
3. Show matching videos (url/thumbnail already in index)

Regenerate from `tenkV.json`:

```bash
py -3 batch_bwt_videos.py
```
