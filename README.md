# Task 06: Constructing and Evaluating Synthetic Media

> **Synthetic media disclosure.** Every audio file in this repository is
> AI-generated. None of the voices are real people. The clips were made with
> text-to-speech tools for a research assignment, and each one opens with a spoken
> line stating that it is synthetic. Nothing here should be treated as a recording
> of a real person.

## What this project is

This project takes a written narrative and turns it into synthetic speech, then
looks honestly at how convincing the result is and where it gives itself away.

The narrative is my own analysis from Task 5, the coaching read on the 2024
Syracuse University Women's Lacrosse season (focus on offense, build around the
leading scorer). Reusing real analytical content mattered here. A synthetic voice
reading a genuine argument surfaces different things than a voice reading filler.

I generated the same short script through two different text-to-speech systems so
I could compare them directly. The interesting part was not any single clip, it
was hearing the two side by side and noticing where the gap actually lives.

## The two approaches

1. **ElevenLabs**, using the preset voice "Roger."
2. **Fish Audio**, using the preset voice "Sarah."

Both were run on their free tiers. The exact settings, the full comparison, and
my notes on what worked and what slipped are in `PROCESS_LOG.md`.

## Short version of what I found

The ElevenLabs clip was the more convincing of the two. It sounded like a person
speaking rather than a machine reading, with a distinctive, warm quality to the
voice and pacing that felt natural. It handled the pauses especially well,
including the longer, more deliberate ones, which is usually where synthetic
speech stumbles.

The Fish Audio clip was strong on its own terms and would have impressed me in
isolation. Placed next to the ElevenLabs version, though, it read as slightly more
robotic, a little flatter in rhythm and missing some of the small human variation
that made the first clip feel alive.

The takeaway is that the giveaway in current text-to-speech is rarely the sound of
the voice itself. It is the cadence and the pauses. That is the seam to listen for.

Running both clips through an AI-voice detector added a twist. The Fish Audio clip
was flagged confidently as synthetic. The ElevenLabs clip produced two conflicting
verdicts at once, a 95% "authentic" headline score sitting directly above a written
analysis that called it strongly AI-generated. The fuller version of that finding
is in `PROCESS_LOG.md`, and it turned out to be the most interesting result of the
whole task.

## Files in this repository

| File | What it is |
| --- | --- |
| `source_script_SYNTHETIC.txt` | The script both clips were generated from, with the spoken disclosure line |
| `SYNTHETIC_elevenlabs_roger.mp3` | Approach 1, generated with ElevenLabs (voice: Roger) |
| `SYNTHETIC_fishaudio_sarah.mp3` | Approach 2, generated with Fish Audio (voice: Sarah) |
| `PROCESS_LOG.md` | Tool details, settings, the full evaluation, and time spent |
| `README.md` | This overview |

_Note: rename your two audio files to the names above (or update this table to
match whatever you name them) so the filenames themselves show the clips are
synthetic._

## How to reproduce

1. Open `source_script_SYNTHETIC.txt` and copy the script, including the spoken
   disclosure line at the top.
2. Paste it into ElevenLabs text-to-speech, pick the Roger voice, generate, and
   download the audio.
3. Do the same in Fish Audio with the Sarah voice.
4. Listen to both back to back and compare cadence, pauses, and how each handles
   the player name and the numbers.

## A note on scope

This is a research exercise, not a polished production. The point was to build the
artifacts, break them down honestly, and learn where the current tools hold up and
where they do not. Both voices used are generic presets provided by the tools, not
clones of any real person.