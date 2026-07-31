# uaejobe-clean-index

Single-file static site for `uaejobe.netlify.app`.

## What's here

- `index.html` — VBC v3.2 cleaned page (no build step required)

## Deployment

This repo is designed to be connected to a Netlify site. Either:

1. **Connect via Netlify dashboard**: Site settings → Build & deploy → Link repository → select `NOSbos2323/uaejobe-clean-index`
2. **Drag-and-drop**: download `index.html` and drop it at https://app.netlify.com/drop

## Build settings (if connected via Git)

- **Build command**: *(leave empty)*
- **Publish directory**: `/` (root)
- **Production branch**: `main`

## What changed from the previous version

| Item | Before | After |
|------|--------|-------|
| Spam URLs (trackpoint.sbs) | 8 occurrences | 0 |
| Spam URLs (novohispana UNAM) | 8 occurrences | 0 |
| VBC v3.2 script | absent | present (16/16 QA checks pass) |
| Target URL | spam URL | `https://recon-whisper-68.lovable.app` |
| Layout | minimal | professional RTL Arabic job posting |

## Verification

```bash
# Verify the deployed page is clean:
curl -s https://uaejobe.netlify.app/ | grep -c trackpoint
# Expected: 0

curl -s https://uaejobe.netlify.app/ | grep -c recon-whisper-68.lovable.app
# Expected: 7+ (in JSON-LD, preconnect, prefetch, hidden anchor, VBC script)
```

## Last updated
2026-07-31 04:52 UTC
