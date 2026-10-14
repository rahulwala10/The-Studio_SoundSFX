**The Studio Sound v1.1**: lighter on the iPhone.

Open it: https://rahulwala10.github.io/The-Studio_SoundSFX/

**Why**
On the iPhone the page could get stuck on "Loading project", for example after an export. Safari closes a page that uses too much memory, and the page then reloaded into a screen that never finished.

**What changed**
- **About half the memory at its highest, about five times less while you work in Sounds.** Measured with the same 31-second Reel and the same steps in a phone-sized Chromium:

  | Step | v1.0 | v1.1 |
  |---|---|---|
  | Captions made | 796 MB | 254 MB |
  | Sounds ready | 1,240 MB | 275 MB |
  | Five music tracks tried | 1,567 MB | 332 MB |
  | Sound track saved | 1,571 MB | 302 MB |
  | Captioned video exported | 1,554 MB | 848 MB |

- **The speech model is let go** 15 seconds after it writes your captions (it was kept for the whole visit). It loads again for the next project.
- **Only the sounds your Reel plays are kept.** Music is cut to your Reel's length, and trying another track lets go of the last one.
- **Export comes first.** When an export starts, every sound and the audio clock are let go; they come back when you press play.
- **Cuts in the video on a phone** are found on the app's light preview copy, never on the full-size original. On the laptop nothing changes.
- **A way out.** If a project is still loading after 20 seconds, the screen offers **Open again** and **Back to projects**. Your project is saved either way.
- Sounds, rules and the library are unchanged (the sounds zip is the same as v1.0).

**Downloads**
- `the-studio-sound-v1.1-windows.zip` and `the-studio-sound-v1.1-sounds.zip`: the laptop copy. Unzip both in the same place, then double-click `Start The Studio Sound.bat` (http://localhost:5179).
- `source/the-studio-sound-source.zip` (repository root): the full source code.

Built on [tscaps](https://github.com/francozanardi/tscaps) by Franco Zanardi (engine and templates MIT, editor AGPL-3.0).
