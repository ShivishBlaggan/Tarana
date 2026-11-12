# Tarana

A clean, ad-free music player for Android. Local library, streaming, offline downloads, synced lyrics, and a queue that actually behaves.

Tarana is a **free and open source project**. It's built on top of the open source Android music ecosystem — the players, libraries and tools that came before it — and it wouldn't exist without them.

---

## Download

Grab the latest `Tarana.apk` from [Releases](../../releases) and install it (allow "install unknown apps" for your browser or file manager).

| | |
| --- | --- |
| Version | 1.5.0 (169) |
| Package | `echo.music.iad1tya` |
| Min Android | 8.0 (API 26) |
| Target | Android 16 (API 36) |
| Size | ~148 MB |

The APK is signed with a self-signed release key. Install over older builds only if they came from this repo; otherwise uninstall first.

## What's inside

- **Playback** — gapless queue, shuffle/repeat, crossfade, audio focus handling, MediaSession controls on the lock screen and in the notification shade
- **Library** — songs, artists, albums, playlists and folders, indexed instantly from device storage
- **Search** — local library plus online catalog results
- **Streaming & downloads** — play online or save tracks for offline listening
- **Lyrics** — synced lyrics view and a full-screen lyric mode
- **Music Flow** — endless related tracks from any song
- **Equalizer** — built-in EQ with bass and surround controls
- **Sleep timer, playback speed, skip silence**
- **Backup & restore** — export and import your library and settings
- **Cast & Listen Together** — send audio to a TV or speaker, or sync playback with friends
- **Widgets and a quick settings tile**
- **Material 3 UI** with light/dark theming and dynamic color
- **No ads, no trackers, no account needed** for local playback

## Updates

Tarana updates itself. **Settings → Search → "System update"** checks this repository's latest GitHub release, compares it to the installed version, and if a newer one exists it downloads the APK and hands it to the Android installer — all inside the app. No browser, no redirects, no third-party download pages.

To publish an update:

1. Bump `versionName` / `versionCode`.
2. Create a release tagged `v1.5.1` (the leading `v` is stripped before comparing versions).
3. Attach the new APK to that release — the updater reads `tag_name`, `body` (changelog) and `assets[].browser_download_url`.
4. Write the changelog as the release notes; that's what the app displays.

Drafts and pre-releases are ignored, so don't publish those if you want the update to go out.

## Building

The released APK is produced from the decoded resource/smali tree:

```bash
java -jar tools/apktool.jar b apk-work/echo -o apk-work/unsigned.apk
zipalign -f -p 4 apk-work/unsigned.apk apk-work/aligned.apk
apksigner sign --ks your.keystore --out Tarana.apk apk-work/aligned.apk
```

Sign with your own key if you rebuild — the published keystore is not included, and builds signed with a different key can't install over the official one.

## Notes

- Verified on Android 15: MediaSession reports `PLAYING`, playback position advances, and there are no startup crashes.
- Some features need network access (streaming, catalog search, lyrics, artwork).
- This project is distributed under the GPL-3.0. See `LICENSE`.

## Credits

Tarana exists because of the open source community that built the Android music player ecosystem — every library, player and utility this project stands on. Thank you to everyone who publishes their work openly.

Maintained by [Shivish](https://github.com/ShivishBlaggan).

**An open source project, made with open source.**
