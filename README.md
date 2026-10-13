# The Studio Sound

**Captions, sound effects and background music for Reels, by Rahul Wala.**

Open it: **https://rahulwala10.github.io/The-Studio_SoundSFX/**

How it works: **https://rahulwala10.github.io/The-Studio_SoundSFX/how-it-works.html**

The Studio Sound is [The Studio Captions](https://rahulwala10.github.io/The-Studio---Transcription-and-Typology-repository/)
plus a **Sounds** tab. Drop in a Reel: it writes the captions from your voice,
then listens to what you say and places sound effects and a music bed that fit
it, always under your voice. Everything runs in your browser, on your iPhone or
laptop. Your video is never uploaded.

## The Sounds tab

- **Subtle, Punchy or Off.** Subtle (the default) puts a few soft sounds on the
  moments that matter. Punchy adds more, a little louder, with fun touches.
- **It listens for moments with a job:** the hook in the first seconds, a new
  point after a pause, list items ("first", "second"), a twist ("but"),
  money, good news, photos and messages, the call to action ("follow",
  "save"), and cuts in the video.
- **Tone first.** Each sentence is scored for sentiment, so a sad or serious
  line never gets a playful sound, and the music bed is picked to match the
  mood (upbeat, chill, inspiring, emotional, tension, cinematic, playful, tech
  or desi).
- **Never louder than you.** Your voice is measured the broadcast way (ITU-R
  BS.1770). Every effect is set against it and never goes above it; the music
  sits 15 to 18 LU under your voice, dips while you talk and rises a little in
  the gaps.
- **Hear it, change it.** The preview plays the sounds and music with the
  video. Play any sound on its own, mute it, swap it, change the music, or
  move the effects and music levels.
- **Save the sound track** as a short video for Instagram's Edits app (Audio →
  Import) or a WAV for CapCut, then lay it under your captioned video.

The full rules, numbers and research are in [SOUND-RULES.md](SOUND-RULES.md).

## The sound library

119 sound effects in 34 kinds (whooshes, swipes, risers, hits, pops, clicks,
dings, cash registers, camera shutters, sparkles, typing and more) and 32
music beds in nine moods, shipped inside the app. Every file is CC0 or public
domain, so it is free to use in your Reels, monetised or not, with no credit
needed: Freesound (CC0 only), Kenney audio packs (CC0) and FreePD music
(public domain). Each file is listed with its source in
[sounds/CREDITS.md](sounds/CREDITS.md).

## Releases

- `releases/v1.0/`: the first release. For the laptop, unzip
  `the-studio-sound-v1.0-windows.zip`, then unzip
  `the-studio-sound-v1.0-sounds.zip` in the same place (it fills
  `app/sounds/`), and double-click `Start The Studio Sound.bat`. It opens at
  http://localhost:5179. The two parts are split to stay under GitHub's file
  size limit.

## Built on tscaps

The Studio Sound is built on [tscaps](https://github.com/francozanardi/tscaps),
the open-source caption editor by Franco Zanardi. Its engine and templates are
MIT-licensed (`LICENSE-engine-MIT.txt`), and its editor app is AGPL-3.0
(`LICENSE-editor-AGPL-3.0.txt`). As the AGPL asks, the full source of this
version is here, in `source/the-studio-sound-source.zip`; the sound files
themselves are in `sounds/`.

This repository holds the built site that GitHub Pages serves, plus the source
and the Windows laptop package for each release under `releases/`.
