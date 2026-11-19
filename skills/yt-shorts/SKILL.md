---
name: yt-shorts
description: >-
  Make an original vertical AI cinematic Short from an idea, or find the Shorts hiding inside a long video and write them, using the
  transcript to pick self-contained moments. Use for "cut this into shorts",
  "clip this", "repurpose this video", "what should I clip".
---

# yt-shorts

## Choose the source

For an idea, brief or request to generate scenes, use Original below. For a request to clip a supplied long video, use Picking and Writing each one. If both are supplied, follow the requested deliverable. Ask for a transcript only for extraction.

## Original cinematic Short

Take the premise, category (VFX, Creative or Experience), duration, language and any visual references. If unspecified, draft a 15-second 9:16 Short in three beats. Give the first frame a visible change or question, develop it with one action per shot and pay it off on screen. Use a single uninterrupted shot if requested. Read the voiceover aloud for timing, or write “ambient only” when the visuals carry the story.

Return one copyable production record with the idea, category, hook, timed script, generation prompts, title, description, relevant hashtags, thumbnail frame, upload notes, stage and production notes. Keep the title and description with the prompts. Describe fiction accurately. For historical subjects distinguish sourced details from invented visual details.

1. Lock the recurring character, clothing, prop, location, lighting and direction of travel in one visual reference. Repeat the relevant details in **each** standalone prompt. Identify what changes intentionally.
2. Give all numbered still-image prompts together, then matching numbered image-to-video prompts in the same order. Specify shot duration, framing, starting pose, one action, camera movement and final frame. Durations must add to the requested runtime. For one continuous shot, give one starting image and one motion prompt with timed beats.
3. Have the creator approve the reference still first. Use the approved still for its matching clip. Where supported, use the previous clip’s last frame as the next start for continuous action. For a deliberate cut, describe the matching prop state, hand and screen position. Generate clean visuals and add any captions during editing.
4. List the manual tasks: generate clips, check neighboring frames, assemble, add voice or ambience, pick a thumbnail frame, review metadata, watch the exported file. If a prop jumps or a face changes, regenerate the affected shot against its approved reference. Mark the stage Ready to Upload only after the creator reviews the export. The creator handles Studio and publication.

## Transcript extraction

A Short cut out of a long video is not a clip of the best moment. It is a moment that **survives
without the video around it**, which is a much smaller set.

## Picking

Read the transcript and find spans of 20-55 seconds where all three are true:

1. It opens on a complete thought. If the first sentence needs the previous minute, it is not a Short.
2. There is a turn in it - a claim, then something that complicates or proves it.
3. It ends on a line, not a trail-off.

Rank the candidates and show the user the top five with their timecodes and first line, so they can
reject one without reading the whole transcript.

## Writing each one

- **A NEW first line.** The long video's line assumes context this viewer does not have. Write the
  replacement and run it through `../yt-script/hookscore.py`.
- **On-screen text for the first two seconds**, different words from the spoken line.
- **A loop point**: what the last line sets up so the first line answers it.
- Vertical framing note - what gets cropped out of a 16:9 frame and whether that matters.

## The gate

Nothing here publishes. This skill writes and you publish. Every output ends in a block the user
copies, and the last line of every run is the question: **ship it, or change it?**
