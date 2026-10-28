# Afterglow Streaming

A personal streaming-style media player that runs entirely in your browser. Point it at a folder of movies and TV shows on your computer and you get a Netflix-like library with posters, descriptions, resume-where-you-left-off, subtitles and a seek bar with preview thumbnails.

It is a single file (`player.html`). There is no server, no account and no install.

## Quick start

1. Open `player.html` in **Chrome or Edge**.
2. Click **Choose Content folder** and select your `Content` folder (see [Folder layout](#folder-layout)).
3. Wait a moment while posters and descriptions load, then press play.

The app remembers your folder, so next time you only need to open the file. If the browser asks for permission again, click **Reconnect folder**. Your history and list are kept.

If the folder picker doesn't appear when you open the file directly, serve the folder it sits in locally and open that address instead:

```
python3 -m http.server 8000
```

Then visit `http://localhost:8000/player.html`.

## Folder layout

Pick the folder that contains a `Shows` folder and a `Movies` folder. Videos can sit in subfolders.

```
Content/
├── Shows/
│   └── Breaking_Bad/
│       ├── Breaking_Bad__s01_e01.mp4
│       ├── Breaking_Bad__s01_e01.srt        (optional subtitles)
│       └── Breaking_Bad__s01_e02.mp4
└── Movies/
    ├── The_Dark_Knight_(2008).mp4
    └── Spirited_Away_2001.mp4
```

**Shows** must be named `Show_Name__sXX_eYY.ext`. That is two underscores, then the season and episode numbers. Single underscores in the name become spaces.

**Movies** are named `Movie_Title_(Year).ext` or `Movie_Title_Year.ext`. The year is optional but helps find the right poster and description.

## Supported formats

| Works almost everywhere | Depends on your browser and codecs |
| --- | --- |
| MP4 (H.264 video, AAC audio), WebM | MKV, AVI, MOV, WMV, TS, M4V, OGV |

The app scans for all of the formats above, but your browser decides what it can actually play. If a file won't play, convert it to MP4 (H.264/AAC).

## Features

**Library**
- Home page with a featured title, Continue watching, Recently added, My list, genre rows, Movies and TV shows
- Posters, descriptions, genres, ratings and episode titles fetched automatically
- Search by title, episode name, or `show s1e3`
- "Surprise me" picks something at random
- Progress is saved automatically, and you can remove an item from Continue watching with the ✕ on its poster

**Player**
- Seek bar with preview thumbnails, generated in the background for instant scrubbing
- Subtitles: `.srt` and `.vtt` files with the same name as the video load automatically. You can also drop a file onto the player or right-click the CC button
- Playback speed from 0.5× to 2×
- Picture-in-picture, fullscreen, remembered volume, and a remaining-time toggle (click the time)
- Next episode button near the end of an episode, with auto-play of the next episode
- Media key support and the current title shown in the browser tab
- Double-click the left or right side of the video to skip 10 seconds

**Personalization** (Settings)
- Name, accent and highlight colors, five background themes, favicon (ring, play, letter, emoji or your own image)
- Poster size, heading font, film grain
- Default speed, subtitle size, thumbnail previews on or off
- Export and import a backup of your history, list and settings

## Keyboard shortcuts

| Key | Action |
| --- | --- |
| `Space` / `K` | Play or pause |
| `←` `→` / `J` `L` | Seek 10 seconds (hold `Shift` for 5) |
| `↑` `↓` | Volume |
| `0`–`9` | Jump to 0–90% of the video |
| `<` `>` | Playback speed |
| `C` | Subtitles on or off |
| `I` | Picture-in-picture |
| `F` | Fullscreen |
| `N` / `P` | Next or previous episode |
| `S` | Next episode (when the button is showing) |
| `M` | Mute |
| `Home` / `End` | Start or end |
| `?` | Show shortcuts |
| `Esc` | Close the player |
| `/` | Focus search (outside the player) |

## Privacy and data

- Your videos never leave your computer. They are read directly from disk by the browser.
- The only network requests are metadata lookups, which send titles and years to [TVMaze](https://www.tvmaze.com) (shows), [iTunes Search](https://performance-partners.apple.com/search-api) and Wikipedia (movies), plus a poster image search as a last resort. No keys or accounts are needed.
- Watch progress, My list, settings and the metadata cache are stored in your browser (localStorage and IndexedDB). They stay on this browser and device, so use **Export backup** in Settings to move them elsewhere.

## Troubleshooting

| Problem | Fix |
| --- | --- |
| "Your browser can't play this file" | The codec isn't supported. Convert to MP4 (H.264/AAC), or try Edge or Chrome |
| No `Shows` or `Movies` folder found | Select the folder that contains them, not one of them directly |
| A show doesn't appear | Check the file name follows `Name__s01_e01.mp4` and sits under a `Shows` folder |
| Wrong poster or description | Make the file name closer to the real title (add the year for movies), then **Settings → Clear metadata cache** |
| Posters or descriptions missing | Check your connection and any ad blocker, then press **Refresh** |
| "Metadata rate limit hit" | The free lookup services limit requests. Wait a minute and press **Refresh** |
| Folder permission keeps expiring | Click **Reconnect folder**. Browsers may ask again after a restart |
| Playback stutters while scrubbing on very large files | Turn off **Seek bar preview thumbnails** in Settings |
| Browser without folder memory (Firefox, Safari) | You can still choose the folder each visit. Your history and list are saved |

## Known limitations

- Only one subtitle track is loaded automatically per video, and there is no language picker.
- Metadata depends on free public services and can occasionally match the wrong title.
- There is no intro detection or skipping.
- Chrome and Edge give the best experience because they can remember your folder.

## Project structure

Everything lives in `player.html`: markup, styles and scripts. There are no dependencies and no build step. Fonts (Fraunces and DM Sans) load from Google Fonts and fall back to system fonts when offline.
