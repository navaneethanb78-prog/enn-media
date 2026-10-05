# ENN Consultancy — campaign media

Public image files for the ENN outreach orchestration. Meta's servers fetch the
WhatsApp header image from here directly, so this repository must stay **public**
and these paths must not change.

---

## Your URL base

After you upload this to GitHub, every file is reachable at:

    https://raw.githubusercontent.com/<YOUR-USERNAME>/enn-media/main/<path>

Replace `<YOUR-USERNAME>` once and the whole table below is live.

---

## 1. WhatsApp template header — the one that must work

| File | Used by | URL |
|---|---|---|
| `whatsapp/iso9001-2026-transition.png` | `enn_iso2026_transition_v1` image header | `https://raw.githubusercontent.com/<YOU>/enn-media/main/whatsapp/iso9001-2026-transition.png` |

1254 x 1254, 211 KB. This is the URL to send me — it goes into `HEADER_IMAGE_URL`
in `Plan WA Sends`.

`whatsapp/iso9001-2026-transition-2x.png` is the 2508 px version for print or a
banner crop. Not used by the orchestration.

---

## 2. Sector posters — 1080 x 1350 (4:5 portrait)

Nine files, named to match the `poster_key` the orchestration already computes in
`Build Queue Rows`. The key maps 17 `sector_key` values onto these nine.

| poster_key | File | sector_key values that land here |
|---|---|---|
| auto | `posters/auto.png` | auto |
| aerospace | `posters/aerospace.png` | aerospace |
| medical | `posters/medical.png` | medical |
| pumps | `posters/pumps.png` | pumps |
| precision | `posters/precision.png` | precision |
| foundry | `posters/foundry.png` | foundry, fabrication |
| textilemc | `posters/textilemc.png` | textilemc |
| surface | `posters/surface.png` | surface |
| general | `posters/general.png` | plastics, electrical, food, engservices, epc, logistics, general, excluded |

URL pattern:

    https://raw.githubusercontent.com/<YOU>/enn-media/main/posters/<poster_key>.png

---

## 3. Sector banners — 1875 x 625 (3:1 landscape)

Same nine keys, wide format. Suited to email headers.

    https://raw.githubusercontent.com/<YOU>/enn-media/main/banners/<poster_key>.png

---

## Which shape goes where

| Use | Best shape | What is here |
|---|---|---|
| WhatsApp template header | 1.91:1 landscape | the transition poster is 1:1 square; WhatsApp crops a centre square in the chat preview, full image on tap |
| Email header | 3:1 or wider | `banners/` fit well |
| Social post / print | 4:5 portrait | `posters/` |

The square transition poster works as a WhatsApp header, but the headline and the
contact bar can be cropped out of the small chat preview. A 1.91:1 version would
avoid that — ask and it can be produced.

---

## Rules for this repository

1. **Keep it public.** Meta fetches anonymously. A private repo returns 404 and
   every WhatsApp send fails with error `131053`.
2. **Do not rename or move files.** The paths are hardcoded in the orchestration.
   To change an image, upload a new file over the same name.
3. **Use the `raw.githubusercontent.com` URL**, not the `github.com/.../blob/...`
   one. The blob URL returns an HTML page, not the image bytes.
4. Keep each file under 5 MB. All current files are well inside that.

## Checking a URL works

Paste it into a browser. You must see **only the image** on a blank background.
If you see a GitHub page with menus, you copied the blob URL instead of the raw one.
