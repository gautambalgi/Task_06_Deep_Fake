# Process Log

A running record of how I built and evaluated the synthetic audio for this task.

## Source material

The script is drawn from my Task 5 analysis of the 2024 Syracuse Women's Lacrosse
season, condensed to about 130 words and rewritten to be read aloud. It opens with
a spoken line stating that the voice is AI-generated. The full text is in
`source_script_SYNTHETIC.txt`.

I kept the script identical across both tools so the only variable was the
synthesis engine itself.

## Approach 1: ElevenLabs (voice: Roger)

- **Tool:** ElevenLabs, free tier
- **Voice:** Roger, a preset described as laid-back, casual, and resonant
- **Settings:** default preview settings for stability, similarity, and style
- **Output:** MP3
- **Rough time spent:** [fill in, for example 10 to 15 minutes including a couple
  of regenerations]

## Approach 2: Fish Audio (voice: Sarah)

- **Tool:** Fish Audio, free tier
- **Voice:** Sarah, a preset voice
- **Settings:** default settings
- **Output:** MP3
- **Rough time spent:** [fill in]

## Evaluation and comparison

Listening to the two clips back to back was the most useful part of this whole
exercise, because the difference between them only became obvious once I could put
them directly against each other.

The ElevenLabs clip, Roger, was the stronger of the two by a clear margin. It
genuinely sounded like a person talking rather than a machine reading text. The
voice had a texture and a warmth to it that felt specific and human, not generic,
and the pacing was the thing that really sold it. The pauses fell exactly where a
real speaker would take a breath, and even the longer, more deliberate pauses in
the middle of the narration were handled cleanly, with none of the rushed or
clipped feeling that usually gives synthetic speech away. If someone had played me
this clip without warning, I am not confident I would have picked it as AI.

The Fish Audio clip, Sarah, was good too, and taken on its own I would have been
impressed by it. The voice was clear, the delivery was smooth, and there was
nothing obviously wrong with it. But the side by side is unforgiving. Once my ear
had the ElevenLabs version as a reference point, Sarah started to feel a little
more robotic. The rhythm was slightly flatter and more even than a person would
naturally speak, and it was missing some of the small shifts in emphasis and the
tiny imperfections that made Roger feel alive. It is the sort of thing you would
likely never notice in isolation, but next to the other clip it is real and
audible.

**What this tells me about the failure modes.** The interesting finding is that
the giveaway in modern text-to-speech is rarely the raw sound of the voice. Both
voices sounded clean and believable at the level of individual words. The seam is
in the prosody, the cadence and the pauses. The tool that got the timing and the
breathing right felt human, and the tool that was a fraction too even felt
synthetic, even though on paper both produced a clear, natural voice. Pacing, not
tone, is where I would listen for the fake.

**Would either fool a casual listener?** Probably yes, both would pass a quick
listen from someone not paying close attention. The ElevenLabs clip would pass a
much closer listen than the Fish Audio one. The gap only opens up under direct
comparison or careful attention.

## Iteration notes

Running the same script through two engines was the right call. A single clip
would have told me the technology is good. The comparison told me something more
specific and more useful, which is where the remaining weakness actually sits and
how small the margin between convincing and slightly off has become.

## Detection and provenance check

I ran both clips through the same acoustic detector to see whether the audio could
be flagged as synthetic, and whether the tool agreed with my own ear.

- **Detector used:** Undetectable.ai AI Voice Detector (powered by TruthScan),
  analyzing the first 30 seconds of each clip.

### Fish Audio (Sarah)
- **Result:** Likely AI-Generated, 1% real.
- **Read:** A confident and correct catch. This matched my own impression, since
  Sarah was the clip that sounded slightly more robotic to me.

### ElevenLabs (Roger)
- **Result:** This one was genuinely strange, and it is the most interesting
  finding of the whole task. The headline score said 95% authenticity, "Likely
  Authentic." But the written summary directly underneath said the opposite: it
  described the audio as strongly indicative of AI-generated speech, flagged the
  flat and highly consistent intonation as a hallmark of AI, and pointed to the
  lack of organic background noise as a sign of synthetic origin.
- **Read:** The tool contradicted itself. Its top-line number said real human,
  while its own detailed analysis said synthetic. So the detector both passed and
  caught the same clip at the same time.

### What this means

Put next to my listening notes, the three results line up into a clear story.

My ear said Roger was the most human of the two. The detector's headline score
agreed with my ear (95% authentic). But the detector's deeper analysis caught
Roger anyway, and it caught it on exactly the thing I had noticed myself, the
unnatural evenness in the pacing and the absence of the small imperfections a real
recording carries. Meanwhile Sarah, which sounded a little more synthetic to me,
was flagged hard at 1% real.

The pattern is that the more convincingly a voice fools a human listener, the more
it can also inflate a detector's top-line score, yet the underlying acoustic tells
are still sitting there for anything that reads past the number. The better fake
does not remove the evidence, it just hides it from a quick glance.

### Honest caveat

According to me No AI voice detector is perfect, and accuracy drops on compressed audio like these
MP3s. The Roger result is a good reminder of that on its own, since the tool
produced two conflicting verdicts for one clip. Any single score here is best
treated as a probability and a prompt to look closer, not as proof. I would want a
second tool, or the provenance route below, before calling any result final.
