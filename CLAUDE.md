# mrgng — Project Context for Claude

## What this is
Band portfolio website for **Mr. GnG** (mrgng), a two-piece rock band (Ishan Dave in India, Abhilash Sreekumar in France). Live at **mrgngofficial.com**, hosted on GitHub Pages. Pushing to `main` deploys in ~30 seconds.

## Stack
Single file. The entire site — all content, styles, and JS — lives in `index.html`. No framework, no build step, no dependencies to install.

## Files
| File | Purpose |
|---|---|
| `index.html` | The entire website |
| `razed.png` | R.A.Z.E.D movie poster — used as hero image |
| `razed.jpg` | R.A.Z.E.D YouTube thumbnail — kept as fallback |
| `bandpic.jpg` | Band photo — used in the photo banner below hero |
| `youtube.jpg` | EPonymous cover art — used in About section |
| `logo.png` | Band logo / favicon |
| `CNAME` | Sets custom domain — do not touch |

## Design system
All defined as CSS variables at the top of `index.html`:
- **Background:** `#080808` (near-black)
- **Accent:** `#d42020` (red) — used for all highlights, buttons, borders
- **Text:** `#ece9e3`
- **Fonts:** Space Grotesk (headings), Inter (body)

## Site sections (in order)
1. **Hero** — R.A.Z.E.D poster split layout (desktop: text left / poster right; mobile: poster as background)
2. **Band photo banner** — `bandpic.jpg` full-width
3. **Press** (`#media`) — Rolling Stone India featured, then Earmilk, BeatCurry, Indigo Music, BraveWords, Metal Shock Finland
4. **Videos** (`#videos`) — R.A.Z.E.D featured, then flat grid of last ~2 years (A Call Away, Paralyse, Xperience Sessions, Silence That Remains, Room 103, Within Unplugged)
5. **About** (`#about`) — band story + interactive release cards (Spotify/Bandcamp embeds) + member bios
6. **Book Us** (`#book`) — mailto form → mrgngofficial@gmail.com

## Spotify / streaming IDs
- **Artist:** `https://open.spotify.com/artist/6jFFWI8mNURdPYM0W1BufB`
- **after Us, The Flood (album):** `319UnXdX7uzKpAVeFey022`
- **R.A.Z.E.D (single):** `7EiW3spjeWjPLKitKVBgwD`
- **EPonymous** is not on Spotify — uses Bandcamp embed (album ID `1067226762`)
- **Apple Music artist:** `https://music.apple.com/us/artist/mr-gng/1632418033`

## YouTube channel
`https://www.youtube.com/@MrGnG464` (channel ID: `UCEnBTwG0c1_gFKAMEW1HUdw`)

## Social links
- Instagram: `https://www.instagram.com/mrgngofficial/`
- TikTok: `https://www.tiktok.com/@mrgngofficial`
- Bandcamp: `https://mrgng.bandcamp.com/`
- Booking email: `mrgngofficial@gmail.com`

## How to make changes
Edit `index.html`, then:
```
git add index.html
git commit -m "describe what you changed"
git push
```
Site updates in ~30 seconds.

## Common tasks
**Add a music video:** Find the section `<!-- R.A.Z.E.D — featured -->` in the videos section and add a new `.video-card` to the `.video-grid` below it. Use the YouTube video ID in the embed src.

**Add a press article:** Find the `#media` section and add a `.media-card` to the `.media-grid`. Copy an existing card's structure.

**Update the hero for a new release:** Change the `razed.png` src and the hero text/CTA to point to the new release.

**Add album art for *after Us, The Flood*:** Drop the image file into the repo folder, then replace the text placeholder in the `.ep-art` div inside the "after Us, The Flood" ep-card with an `<img>` tag (same pattern as the EPonymous card which uses `youtube.jpg`).

## Things still to do
- [ ] Proper album cover art for *after Us, The Flood* (text placeholder currently)
- [ ] Any new press articles — add to `#media` section
- [ ] Upcoming shows section if the band starts touring
