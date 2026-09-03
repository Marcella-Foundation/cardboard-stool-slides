# Why Cardboard Works

Seven structural concepts for the cardboard stool build. Each slide pairs a
vocabulary word and a plain-language definition with a short video showing the
idea holding and failing side by side.

Open `index.html` — no build step. Slides are addressable by URL fragment,
e.g. `#3-triangles`, `#5-buckling`.

**Live:** https://cardboard.slides.atriumtahoe.org

## Where the videos live

The clips are **not** in this repo. They are served from R2 in the Marcella
Foundation Cloudflare account, so this repo stays small:

    https://assets.slides.atriumtahoe.org/video/<file>

| Slide | Concept | Video | Poster |
|---|---|---|---|
| 1 | Grain direction | `crush_15s.mp4` | `poster.png` |
| 2 | Stiffness | `beam_15s.mp4` | `beam_poster.png` |
| 3 | Triangulation | `brace_15s.mp4` | `brace_poster.png` |
| 4 | Redundancy | `spread_15s.mp4` | `spread_poster.png` |
| 5 | Buckling | `buckle_15s.mp4` | `buckle_poster.png` |
| 6 | Lamination | `glue_15s.mp4` | `glue_poster.png` |
| 7 | Load path | `path2_15s.mp4` | `path2_poster.png` |

Bucket: `cardboard-slides` · account `Sean@marcellafoundation.org`

To re-upload after regenerating a clip:

```bash
export CLOUDFLARE_ACCOUNT_ID=b08f3c47604042d9401f88f7dc4fa12a
wrangler r2 object put cardboard-slides/video/buckle_15s.mp4 \
  --file buckle_15s.mp4 --content-type video/mp4 --remote
```

## Deploying

Cloudflare Pages project `cardboard-slides`:

```bash
wrangler pages deploy . --project-name cardboard-slides --branch main
```

Custom domains: `cardboard.slides.atriumtahoe.org` and
`slides.atriumtahoe.org`.
