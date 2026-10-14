# The Studio - Captions and Sound v1.2

14 October 2026. The Studio Sound gets its new name, and the phone gets a tool of its own.

## What changed

- **New name.** The Studio Sound is now **The Studio - Captions and Sound**. It does everything The Studio Captions did, plus sound, so The Studio Captions has been retired and its address forwards here.
- **The best speech model on the laptop.** New projects start on **Medium**, the most accurate model and the best at Hindi or Hinglish to English captions. The first time it downloads about 940 MB, then it is kept. Smaller models are still under Advanced.
- **Exports go straight into Google Drive.** The first export asks for a folder once (pick Google Drive, The Studio, 05 Finished Reels). After that, videos and sound tracks go straight in, named with the date and the project name, and never overwrite an older file. The Export window shows the folder and has **Change folder**. If the browser ever says no to the folder, the usual Save window opens instead.
- **The Studio - iPhone** is new: https://rahulwala10.github.io/iphone/ . The same captions and sound, with the light Base model and phone settings, and nothing to choose. When a video is ready, **Save to Drive** opens the iPhone's share menu (tap Drive, pick 05 Finished Reels); **Save to Files** keeps it on the phone.

## Speed of the Medium model

Measured on a 31-second Reel on a small 2-core test machine: about 1 minute 45 seconds of speech-to-text with the offline laptop copy, and about 2 minutes 30 seconds on the website (the offline copy can use several processor cores; the website uses one). A normal laptop with more cores is quicker.

## Checked

- Type check, lint, 1,016 of 1,018 app tests (the same 2 tests need video codecs the test machine lacks), plus 17 new tests for the save folder, file names, the iPhone ready screen and the model choice.
- In Chromium against a copy of the site: the laptop tool (Medium by default, the first export asks for the folder once, the second goes straight in as "(2)", the sound track lands in the same folder, no Save window) and the iPhone tool (Base, no model choice, sounds load from the shared library, the ready screen waits, Save to Drive hands over the dated video, Back to the editor, a reload deep inside the app comes back). 26 of 26 checks passed.

## Downloads

The Windows package (`the-studio-captions-and-sound-v1.2-windows.zip`) and the sound files (`the-studio-captions-and-sound-v1.2-sounds.zip`, unzip both in the same place) are kept in Rahul's Google Drive, The Studio, Tool releases, rather than in this repository, to keep it small. The full source of this version is in `source/the-studio-captions-and-sound-source.zip`.
