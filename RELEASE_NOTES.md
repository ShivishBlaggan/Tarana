# Tarana 1.5.2

A clean, ad-free Android music player. Local library, streaming, offline downloads, synced lyrics, and a queue that behaves.

Tarana is a free and open source project, built on top of the open source Android music ecosystem.

---

## Download

Grab `Tarana.apk` from [Releases](../../releases) and install it (allow "install unknown apps" for your browser or file manager).

| | |
| --- | --- |
| Version | 1.5.2 (171) |
| Package | `echo.music.iad1tya` |
| Min Android | 8.0 (API 26) |
| Target | Android 16 (API 36) |
| Size | 147.8 MiB |
| SHA-256 | `eabbb7c6b9abb73d47a70e933ad82c96fa7b6b8b43e0e0f3d4602a76dca111f3` |

Verify with `certutil -hashfile Tarana.apk SHA256` on Windows or `sha256sum` on Linux and macOS.

## What's inside

- **Playback** — gapless queue, shuffle/repeat, crossfade, audio focus handling, MediaSession controls on the lock screen and in the notification shade
- **Library** — songs, artists, albums, playlists and folders, indexed from device storage
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

Tarana updates itself. When a newer release exists, the app downloads the APK and hands it to the Android installer — all inside the app. No browser, no redirects, no third-party download pages.

To publish an update:

1. Bump `versionName` / `versionCode`.
2. Create a release tagged `v1.5.3` (the leading `v` is stripped when comparing versions).
3. Attach the new APK to that release — the updater reads `tag_name` and `assets[].browser_download_url`.
4. Write the changelog as the release notes; that's what the app displays.

Drafts and pre-releases are ignored, so don't publish those if you want the update to go out.

## Building

```bash
java -jar tools/apktool.jar b apk-work/echo -o apk-work/unsigned.apk
zipalign -f -p 4 apk-work/unsigned.apk apk-work/aligned.apk
apksigner sign --ks your.keystore --out Tarana.apk apk-work/aligned.apk
```

Sign with your own key if you rebuild — the published keystore is not included, and builds signed with a different key cannot install over the official one.

## Notes

- Verified on Android 15: playback runs, MediaSession reports `PLAYING`, self-update from an older build completes, and there are no startup crashes.
- Some features need network access (streaming, catalog search, lyrics, artwork).
- Distributed under the GPL-3.0. See `LICENSE`.

## Credits

Tarana exists because of the open source community that built the Android music player ecosystem — every library, player and utility this project stands on. Thank you to everyone who publishes their work openly.

Maintained by [Shivish](https://github.com/ShivishBlaggan).

**An open source project, made with open source.**
