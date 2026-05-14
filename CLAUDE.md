# mrgng — Project Context for Claude

## What this is
Band portfolio website for **Mr. GnG** (mrgng), a two-piece rock band (Ishan Dave in India, Abhilash Sreekumar in France). Live at **mrgngofficial.com**, hosted on GitHub Pages. Pushing to `main` deploys in ~30 seconds.

## Stack
Single file. The entire site — all content, styles, and JS — lives in `index.html`. No framework, no build step, no dependencies to install.

## Git / deploy
- Remote: `https://github.com/harman28/mrgng.git`
- Auth: HTTPS with a GitHub personal access token embedded in the remote URL (run `git remote -v` to check). Token is for user `ishan310464`. If it expires, generate a new one at GitHub → Settings → Developer settings → Personal access tokens → repo scope, then run: `git remote set-url origin https://ishan310464:NEW_TOKEN@github.com/harman28/mrgng.git`
- Push with: `git add <files> && git commit -m "message" && git push`
- If push times out (large images), retry with: `git -c http.postBuffer=524288000 push`

## Files
| File | Purpose |
|---|---|
| `index.html` | The entire website |
| `razed.png` | R.A.Z.E.D movie poster — used as hero image (desktop) and mobile background |
| `razed.jpg` | R.A.Z.E.D YouTube thumbnail — fallback |
| `bandpic.jpg` | Original band photo — used in photo banner below hero (background-position: center 20%, height 520px) |
| `Bandpic Horizontal.jpg` | Horizontal live band shot — displayed full-width between Press and Videos sections, cropped to 220px height showing just the lit strip (object-position: center 30%) |
| `Bandpic_2.jpg` | Second band photo — not yet used, available if needed |
| `youtube.jpg` | EPonymous cover art — used in About section EP card |
| `logo.png` | Band logo / favicon |
| `ishan.jpg` | Ishan Dave — member photo |
| `Abhilash.jpg` | Abhilash Sreekumar — member photo |
| `Vaastu.jpg` | Vaastu — member photo |
| `Meet.jpg` | Meet Gadhia — member photo |
| `rohan shah.jpg` | Rohan Shah — member photo (referenced in HTML as `rohan%20shah.jpg`) |
| `jagdis.jpeg` | Jagdis Jethwa — member photo |
| `CNAME` | Sets custom domain — do not touch |

## Design system
All defined as CSS variables at the top of `index.html`:
- **Background:** `#080808` (near-black)
- **Accent:** `#d42020` (red) — used for all highlights, buttons, borders
- **Text:** `#ece9e3`
- **Fonts:** Space Grotesk (headings), Inter (body)
- **Nav "Book Us" button:** red background (`var(--accent)`) with near-black text (`#080808`)

## Site sections (in order)
1. **Hero** — R.A.Z.E.D poster split layout (desktop: text left / poster right; mobile: poster as background)
2. **Band photo banner** — `bandpic.jpg` full-width (520px tall, position: center 20%, fades into background at top and bottom via gradient overlay)
3. **Press** (`#media`) — Rolling Stone India featured, then Earmilk, BeatCurry, Indigo Music, BraveWords, Metal Shock Finland
4. **Horizontal band photo** — `Bandpic Horizontal.jpg`, cropped to 220px showing only the lit strip
5. **Videos** (`#videos`) — R.A.Z.E.D featured, then grid: Goodbye Mr. GnG, Paralyse, Xperience Sessions, Silence That Remains, Room 103, Within Unplugged
6. **About** (`#about`) — Two-column layout: left = band story text, right = EP/album release cards (Spotify/Bandcamp embeds). Below both columns: full-width 3-column members grid.
7. **Book Us** (`#book`) — mailto form → mrgngofficial@gmail.com (Formspree integration planned but not yet set up)
8. **Footer**

## Members (current — 6 total in a 3-col × 2-row grid)
| Name | Role | Photo file |
|---|---|---|
| Ishan Dave | Vocals · Guitar · Producer | `ishan.jpg` |
| Abhilash Sreekumar | Keys · Drums · Producer | `Abhilash.jpg` |
| Vaastu | Lead Guitar · Live | `Vaastu.jpg` |
| Meet Gadhia | Drums · Live | `Meet.jpg` |
| Rohan Shah | Keys · Live | `rohan shah.jpg` |
| Jagdis Jethwa | Live Musician | `jagdis.jpeg` |

Member cards use class `.member-card-h` with `.member-photo-circle` containing an `<img>`. To add a photo, replace the initials text inside `.member-photo-circle` with `<img src="filename.jpg" alt="Name" />`.

## Spotify / streaming IDs
- **Artist:** `https://open.spotify.com/artist/6jFFWI8mNURdPYM0W1BufB`
- **after Us, The Flood (album):** `319UnXdX7uzKpAVeFey022`
- **R.A.Z.E.D (single):** `7EiW3spjeWjPLKitKVBgwD`
- **EPonymous** — Bandcamp embed only (album ID `147508948`). Not on Spotify.
- **Apple Music artist:** `https://music.apple.com/us/artist/mr-gng/1632418033`

## YouTube videos currently on site
| Title | YouTube ID | Section |
|---|---|---|
| R.A.Z.E.D | `GfBXqhigR98` | Featured (full width) |
| Goodbye Mr. GnG | `PoBnJFXcVdY` | Grid |
| Paralyse ft. Rudy Ayoub | `Eew6-AUDb5s` | Grid |
| Xperience Sessions | `j3CHjHUKvgM` | Grid |
| Silence That Remains | `sH0NfdL0lCU` | Grid |
| Room 103 | `C15ag2-OsAk` | Grid |
| Within (Unplugged) | `6yBhHlzsgn0` | Grid |

## Social links
- Instagram: `https://www.instagram.com/mrgngofficial/`
- TikTok: `https://www.tiktok.com/@mrgngofficial`
- Bandcamp: `https://mrgng.bandcamp.com/`
- YouTube channel: `https://www.youtube.com/@MrGnG464`
- Booking email: `mrgngofficial@gmail.com`

## How to make changes
Edit `index.html` (and add any new image files), then:
```
git add index.html any-new-image.jpg
git commit -m "describe what you changed"
git push
```

## Common tasks
**Add a live show video:** Find `<!-- VIDEOS -->` section, add a new `.video-card` to the `.video-grid` below the featured R.A.Z.E.D card. Use the YouTube video ID in the embed src (use `youtube-nocookie.com` for privacy). User has live footage to upload as unlisted YouTube videos — links to be shared once uploaded.

**Add a press article:** Find `#media` section, add a `.media-card` to `.media-grid`. Copy an existing card's structure.

**Set up Formspree:** User wants to replace the mailto book form with Formspree. Steps: user signs up at formspree.io, creates a form, gets endpoint `https://formspree.io/f/xxxxxxxx`, then update `#bookForm` action attribute and change the JS submit handler to POST to that endpoint instead of opening mailto.

**Update the hero for a new release:** Change the `razed.png` src and the hero text/CTA to point to the new release.

**Add album art for *after Us, The Flood*:** Drop the image file into the repo folder, then replace the text placeholder in the `.ep-art` div inside the "after Us, The Flood" ep-card with an `<img>` tag (same pattern as the EPonymous card which uses `youtube.jpg`).

## Things still to do
- [ ] Formspree integration for Book Us form (user has account to create)
- [ ] Live show footage videos — user uploading as unlisted YouTube, will share links
- [ ] Proper album cover art for *after Us, The Flood* (text placeholder currently)
- [ ] Any new press articles — add to `#media` section
- [ ] Upcoming shows section if the band starts touring
