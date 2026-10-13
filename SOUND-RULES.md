# How The Studio Sound places sounds

The Sounds tab listens to your Reel and places sound effects and a music bed
by rule. Every rule below is in `apps/studio/src/core/sounds/services/SoundPlanner.ts`,
and the numbers come from broadcast standards and listening research (sources
at the end).

## 1. It measures your Reel first

- **Your voice level.** The voice is measured the broadcast way (ITU-R BS.1770
  K-weighting, gated loudness), only over the moments you are speaking. Every
  sound is then set relative to *your* voice, so a quiet recording gets quiet
  effects and a loud one gets louder effects.
- **Pauses and sentences.** From Whisper's word timings: a sentence ends at
  `.`, `?`, `!` or a gap of 0.8 s or more.
- **Cuts in the video.** Frames are compared five times a second (brightness
  and colour histogram); a jump well above the clip's normal movement is a cut.
- **The mood.** Each sentence gets a sentiment score from VADER (a word-based
  model built for social media text). The first sentence counts 1.5 times.
  Speaking rate and how much your voice level moves give the energy.

## 2. The three styles

| | Subtle (default) | Punchy | Off |
|---|---|---|---|
| Sounds | Only moments with a job | More, including fun touches | None |
| Effects under your voice | 12 to 24 dB under | 7 to 20 dB under | |
| Never louder than | voice − 6 dB | voice − 3 dB | |
| Music under your voice | 18 LU under | 15 LU under | none |
| Space between sounds | 2.2 s (1.2 s between two key moments) | 1.0 s | |
| Most sounds | about one per 3.5 s | about one per 2.2 s | |

An effect that lands while you are talking drops a further 3 dB (Subtle) or
2 dB (Punchy). The same kind of sound never repeats within 4 s (Subtle) or
2.5 s (Punchy), except list clicks, which keep a rhythm.

## 3. What gets a sound, in order of importance

| Moment | Example | Subtle | Punchy |
|---|---|---|---|
| The hook: first stand-out word in the first 3.5 s | "**Nobody** tells you this" | soft hit | hit (braam if the line is dark), plus a riser into it |
| Call to action, near the end (one only) | "**Follow** for part two" | notification | ding |
| Good news (the sentence, or the one right after, is clearly positive) | "I finally got the **offer**. I was so happy." | sparkle | success / ta-da |
| List items | "**First**, … **Second**, …" | click | click |
| A twist after a pause | "**But** here's the twist" | (whoosh, as a new point) | record scratch, or a hit if the tone is serious |
| Money | "I spent **£2,000**" | cash register | cash register; a thud if the sentence is negative |
| Photo or message words | "took a **photo**", "she **texted**" | camera / notification | same |
| A new point after a pause | pause of 0.6 s (Subtle) or 0.45 s (Punchy) | swipe / quick whoosh | whoosh |
| A cut in the video | | swipe | quick whoosh |
| A sentence with nothing else | its strongest stand-out word | soft pop (thud if negative), only with 3.5 s of room | pop |
| Typewriter templates (Ealing, Leeds) | every caption | quiet typing | quiet typing |
| The end | last word, with room to ring out | | short sting |

Rules that keep it tasteful:

- **Tone first.** No pop, boing, sparkle or cash register on a negative
  sentence; those get a thud or nothing. Comedy sounds (boing, sad trombone)
  only play in Punchy, only when the whole Reel reads as playful.
- **Sounds with a job win.** A stand-out-word pop only fills a sentence that
  has nothing else, and never crowds a sound with a job.
- **Timing.** People notice a sound more than 45 ms early or 125 ms late
  (ITU-R BT.1359). Whooshes, swipes and risers are lined up so their *peak*
  lands on the moment; hits, clicks and pops start on it.

## 4. The music bed

- **Picked by mood**: upbeat, chill, inspiring, emotional, tension, cinematic,
  playful, tech or desi. A struggle that ends well picks inspiring; a Reel
  about India and home picks desi; a tech topic picks tech. The tempo is
  matched to your energy.
- **Level**: 18 LU (Subtle) or 15 LU (Punchy) under your voice while you talk.
  Research on TV mixes found listeners need speech at least 10 LU above the
  music, and most prefer more; 15 to 20 dB of ducking is common practice.
- **Ducking**: it rises 5 to 6 dB in gaps of 0.8 s or more, and dips again
  0.12 s before you speak (release 0.5 s).
- **Room for your voice**: a high-pass at 80 Hz and a 3 dB dip around 2.5 kHz,
  where speech is clearest.
- **Fades**: 1 s in, 2 s out; loops if the Reel is longer than the track.

## 5. The sound track

The sound track is everything above, without your voice, at 48 kHz stereo,
limited to −1 dBFS so it never clips. Save it as:

- **Video for Edits (.mov)**: a dark one-frame-a-second video with the sound
  track. In Instagram's Edits app, add your captioned video, go to the very
  start, then Audio → Import → this video.
- **Audio file (.wav)**: for CapCut or any editor that takes audio files.

## 6. The library

119 effects in 34 roles and 32 music beds in nine moods, shipped with the app
(about 90 MB). Every file is CC0 or public domain: Freesound (CC0 only), Kenney
packs (CC0), and FreePD music (public domain). Effects are trimmed to their
onset, high-passed at 50 Hz, faded, and normalised to −16 LUFS momentary max
(ambiences −20); music to −20 LUFS. Sounds with little mid-range energy were
left out, because phone speakers roll off below about 800 Hz and those sounds
disappear on a phone. Full credits: `apps/studio/public/sounds/CREDITS.md`.

## Sources

- ITU-R BS.1770, Algorithms to measure audio programme loudness and true-peak
  audio level: https://www.itu.int/rec/R-REC-BS.1770
- EBU R 128, Loudness normalisation and permitted maximum level:
  https://tech.ebu.ch/publications/r128
- Torcoli, Freke-Morin, Paulus, Simon and Shirley, Preferred levels for
  background ducking to produce esthetically pleasing audio for TV with clear
  speech, JAES 2019: https://cris.fau.de/publications/234640600
- ITU-R BT.1359, Relative timing of sound and vision for broadcasting:
  https://itu.int/dms_pubrec/itu-r/rec/bt/R-REC-BT.1359-0-199802-S!!PDF-E.pdf
- Hutto and Gilbert, VADER: A Parsimonious Rule-Based Model for Sentiment
  Analysis of Social Media Text, ICWSM 2014:
  https://ojs.aaai.org/index.php/ICWSM/article/view/14550
