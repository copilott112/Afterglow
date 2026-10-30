# Afterglow Streaming

A personal streaming-style media player that runs entirely in your browser. Choose a folder of movies and TV shows from your computer, or use the built-in YouTube tab to discover and watch YouTube videos without downloading them first.

Enjoy a Netflix-like library with posters, descriptions, resume-where-you-left-off, subtitles and a seek bar with preview thumbnails.

It is a single file (`afterglow-streaming.html`). There is no account or installation required.

**[Download Afterglow Streaming](https://copilott112.github.io/Afterglow/)** · [All releases](https://github.com/copilott112/Afterglow/releases)

![Afterglow Streaming home page](assets/screenshots/home.png)

![Seek bar preview while watching](assets/screenshots/seek-preview.gif)

<p>
  <img src="assets/screenshots/episodes.png" width="49%" alt="Episode list for a TV show">
  <img src="assets/screenshots/settings.png" width="49%" alt="Settings page with themes and colors">
</p>

## Contents

- [Quick start](#quick-start)
- [Folder layout](#folder-layout)
- [Supported formats](#supported-formats)
- [Features](#features)
- [YouTube](#youtube)
- [Keyboard shortcuts](#keyboard-shortcuts)
- [Privacy and data](#privacy-and-data)
- [Troubleshooting](#troubleshooting)
- [Known limitations](#known-limitations)
- [Credits](#credits)
- [License](#license)

## Quick start

1. Download `afterglow-streaming.html` from the [download page](https://copilott112.github.io/Afterglow/) and save it anywhere on your computer.
2. Open it in **Chrome, Edge or another Chromium-based browser**.
3. To watch your own movies and shows, click **Choose Content folder** and select your `Content` folder (see [Folder layout](#folder-layout)).
4. Wait while posters and descriptions load, then press play.

You can also choose **Start with YouTube** on the welcome screen to access YouTube without setting up a local library.

The app remembers your selected folder when browser permissions allow it. If permission expires, click **Reconnect folder**. Your watch history and list are kept.

You can add your own library later using **Add my library**.

## Folder layout

Your selected folder should contain at least one of `Movies` or `Shows`. Folder names are not case-sensitive. Videos can be stored in subfolders.

```text
Content/
├── Shows/
│   └── Breaking_Bad/
│       ├── Breaking_Bad__s01_e01.mp4
│       ├── Breaking_Bad__s01_e01.srt
│       └── Breaking_Bad__s01_e02.mp4
└── Movies/
    ├── The_Dark_Knight_(2008).mp4
    └── Spirited_Away_2001.mp4
```

**Shows** must be named `Show_Name__sXX_eYY.ext`: two underscores, then `s` and the season number (1–2 digits), `_e` and the episode number (1–3 digits). Capital `S` and `E` also work. Single underscores in the name become spaces. Use exactly the same show name in every file, because the name is how episodes are grouped. Files in `Shows` that don't match this pattern are skipped.

**Movies** are named `Movie_Title_(Year).ext` or `Movie_Title_Year.ext`. The year (1900–2099) is optional but helps find the right poster and description. Underscores become spaces.

**YouTube does not use a folder.** It has its own built-in tab and works independently of your local movie and TV library.

## Supported formats

| Works almost everywhere | Depends on your browser and codecs |
| --- | --- |
| MP4 (H.264 video, AAC audio), WebM | MKV, AVI, MOV, WMV, TS, M4V, OGV (all of these are scanned) |

Your browser decides what it can actually play. If a local file won't play, convert it to MP4 (H.264/AAC).

YouTube videos are played through YouTube's embedded player rather than as local video files.

## Features

**Library**
- Top bar with Home, Movies, TV Shows, YouTube and My List, plus search, Refresh (rescan your folders) and Settings.
- Home page with a featured title, Continue watching, Recently added, My List, genre rows, Movies and TV Shows.
- Posters, descriptions, genres and runtime fetched automatically, plus ratings, episode titles and episode images for TV shows.
- Mark movies as watched or unwatched from their page.
- Search by title, episode name, or `show s1e3`.
- "Surprise me" picks something at random.
- Progress is saved automatically, and you can remove an item from Continue watching with the ✕ on its poster.

**Player**
- Seek bar with preview thumbnails, generated in the background for instant scrubbing.
- Subtitles: a `.srt` or `.vtt` file with the same name as the video (or with a language tag, like `Movie.en.srt`) loads automatically. You can also drop a file onto the player or right-click the CC button. UTF-8 and Windows-1252 encodings are handled.
- Playback speed from 0.5× to 2×.
- Picture-in-picture, fullscreen, remembered volume, and a remaining-time toggle (click the time).
- A Next episode button appears in the last 30 seconds of an episode (not on a show's final episode). When an episode ends, the next one starts after an 8-second countdown unless you turn that off in Settings.
- Media key support and the current title shown in the browser tab.
- Double-click the left or right side of the video to skip 10 seconds.

**YouTube**
- Browse trending YouTube videos directly inside Afterglow.
- Search YouTube without downloading videos.
- View video thumbnails, titles, channel names, durations and view counts.
- Discover channels through search results and browse their latest uploads.
- Recently watched videos and recently viewed channels are saved in your browser.
- Open supported videos in the built-in YouTube player.
- Up to five YouTube searches per day. The counter resets at midnight.

**Personalization (Settings)**
- Name, accent and highlight colors, ten background themes, favicon (ring, play, letter, emoji or your own image).
- Poster size, heading font, film grain.
- Default speed, subtitle size, thumbnail previews on or off.
- Home banner, greetings, poster effects and background customization.
- Export and import a backup of your watch history, My List and settings.

## YouTube

Afterglow includes a built-in YouTube browser. You don't need to download videos, save them into a folder or paste individual thumbnail links.

### Discover videos

When you open the YouTube tab, Afterglow displays trending videos. These include thumbnails, titles, channel names, durations and view counts.

### Search YouTube

Use the search field to find videos directly from YouTube.

- Enter a search term and press **Search** or Enter.
- Browse the returned video results.
- Select a video to open it in Afterglow's built-in YouTube player.
- Search results are limited to five searches per day. The limit resets at midnight.

### Browse channels

Afterglow can recognize a channel from suitable search results. When a channel is detected, you can open its channel page and browse its latest uploads.

You can also revisit recently viewed channels.

### Recently watched

Your recently watched YouTube videos are saved in your browser. The YouTube home page displays recently watched videos and channels so you can find them again.

### Watch videos

Selecting a video opens the embedded YouTube player. Afterglow does not need to download the video file to your computer.

Some videos cannot be played inside Afterglow because their owners have disabled embedded playback or because YouTube restricts access. Use **Open on YouTube** when the embedded player cannot play a video.

**Important:** YouTube requires an internet connection. Playback also depends on YouTube's availability and embedding permissions. Opening the HTML directly as a local file may cause YouTube Error 153; using an HTTPS-hosted copy provides the website origin that YouTube's player may require.

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
| `Esc` | Close the shortcuts panel or player. In fullscreen it exits fullscreen first. It also closes the YouTube player. |
| `/` | Focus search (outside the player) |

## Privacy and data

- Your local movie and TV files never leave your computer. They are read directly from disk by the browser.
- The app makes network requests for metadata, artwork and fonts. Titles and years are sent to [TVMaze](https://www.tvmaze.com) (shows), and to the iTunes Search API with Wikipedia as a fallback (movies). Posters come from those services; when no artwork is found, or while metadata is still loading, the app falls back to a Bing image search using the title. Fonts load from Google Fonts.
- YouTube search terms and requests for video and channel information are sent to the YouTube Data API.
- YouTube playback uses YouTube's embedded player. Playback therefore involves requests to YouTube.
- Recently watched YouTube videos and channels, watch progress, My List, settings and metadata are stored in your browser. They stay on this browser and device.
- No local movie or TV files are uploaded to YouTube or other services.

Use **Export backup** in Settings to move your supported saved data to another device.

## Troubleshooting

| Problem | Fix |
| --- | --- |
| "Your browser can't play this file" | The codec isn't supported. Convert to MP4 (H.264/AAC), or try Edge or Chrome. |
| "Could not find a Movies or Shows folder" | Select the parent folder containing `Movies` or `Shows`, not one of those folders directly. |
| A show doesn't appear | Check that its filename follows `Name__s01_e01.mp4` and that it is inside a `Shows` folder. |
| YouTube videos aren't loading | Check your internet connection and any ad blocker. Then try again. |
| YouTube search limit reached | The app allows five searches per day. The counter resets at midnight. |
| YouTube video cannot play | The video owner may have disabled embedded playback. Try **Open on YouTube**. |
| YouTube Error 153 | Open Afterglow from an HTTPS-hosted website instead of directly from a local file. |
| YouTube player doesn't open | Check your connection and whether YouTube is available in your browser. |
| Wrong poster or description | Make the filename closer to the real title (add the year for movies), then use **Settings → Clear metadata cache**. |
| Posters or descriptions missing | Check your connection and any ad blocker, then press **Refresh**. |
| "Metadata rate limit hit" | The free metadata services limit requests. Wait a minute and press **Refresh**. |
| Folder permission keeps expiring | Click **Reconnect folder**. Browsers may ask again after a restart. |
| Playback stutters while scrubbing on very large files | Turn off **Seek bar preview thumbnails** in Settings. |
| Browser without the folder picker (typically Firefox and Safari) | You can still choose the folder each visit. Your history and list are saved. |

## Known limitations

- Only one subtitle track is loaded automatically per local video, and there is no language picker.
- Metadata depends on free public services and can occasionally match the wrong title.
- YouTube requires an internet connection and depends on the YouTube Data API and embedded player.
- YouTube searches are limited to five per day by Afterglow. YouTube's own API quota and availability can also affect results.
- Some YouTube videos cannot be embedded and must be opened on YouTube instead.
- YouTube Error 153 may occur when the HTML is opened directly as a local file. An HTTPS-hosted version provides a website origin.
- There is no intro detection or skipping.
- Chromium-based browsers (Chrome and Edge) give the best experience for remembering your local Content folder.

## Credits

- Show information and images come from [TVMaze](https://www.tvmaze.com). Movie information comes from the iTunes Search API and Wikipedia.
- YouTube video and channel information comes from the YouTube Data API. Playback is provided by YouTube's embedded player.
- Fonts: [Fraunces](https://fonts.google.com/specimen/Fraunces) and [DM Sans](https://fonts.google.com/specimen/DM+Sans) via Google Fonts.
- Afterglow Streaming does not host or provide media. It plays local video files and provides access to YouTube through YouTube's own player.
- Movie and show names, posters and artwork belong to their respective owners and services.

## License

Afterglow Streaming is released under the [MIT License](LICENSE). The license covers this project's code only; posters, metadata and fonts belong to their respective owners and services.
