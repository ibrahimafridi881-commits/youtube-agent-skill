# The YouTube agent skill

Eleven Claude skills that run a YouTube channel. Free, MIT, no signup, no API key, nothing to
connect.

One of them writes your script off 21 hook formulas and scores the hook before you waste a take on
it. One lints the title and the thumbnail as a single pairing, because writing them separately is
why half of your click surface says the same thing twice. One reads your audience-retention export
and tells you the exact second people left and what you were saying when they did. One turns a
transcript into an edit decision list. One finds the Shorts already hiding inside a long video. One
goes and finds what is working in your niche and ranks it by how far each video beat its own
channel, not by how big the channel is.

**Nothing gets published until you do it.** These skills write. You upload.

## Start here on a Windows PC for an original cinematic Short

Download this branch with **Code → Download ZIP**, then **Extract All**. Open the extracted folder containing this README, type `cmd` in File Explorer’s address bar and press Enter. Your working `py` command is enough for the local checks. Run these one at a time:

```bat
py --version
py skills/yt-script/hookscore.py --hook "Why is the clock's shadow ticking backwards?"
py skills/yt-package/title.py --title "The Clock That Lost Its Shadow" --thumb "One tick left"
```

The first tool prints a hook assessment. The second checks title and thumbnail wording. Both are editorial checks. For a text-free thumbnail, review the actual frame on a phone-sized preview. The six scripts use the Python standard library.

**First Short, without installing Claude Code:** open [the Shorts instructions](skills/yt-shorts/SKILL.md), copy the file contents into a chat, then paste this brief:

> Make an original 15-second VFX Short in 9:16. In a Peshawar clock repair shop, a brass clock’s shadow ticks backwards and slips off the wall. Give me a Roman Urdu voiceover, English generation prompts, title and description. Keep the clock above the same blue workbench. Use three five-second shots. Give me all three still prompts together, then all three matching motion prompts. Use the final shadowless wall as the payoff.

Save the resulting record as `clock-shadow.md` in your project folder. Generate the stills and clips in your chosen video tool. At the first cut, compare the clock face, position on the wall and shadow angle. At the second cut, check that the shadow starts where it ended. Assemble the three approved clips in your editor, add sound, then play the exported MP4 from start to finish. Confirm visible frames, audible sound where intended, vertical framing and a clear payoff. As you work, move the record through Idea → Planned → In Production → Ready to Upload. Manually review audience, synthetic-content disclosure, permissions and visibility in Studio when preparing an eligible channel’s upload. Mark Uploaded only after you publish, then Performance Review when data arrives.

### Where each skill fits

| When | Skill | What to do with it |
| --- | --- | --- |
| Before planning, optional | `/yt-viral` | Study a niche outlier’s format and invent a different premise and payoff. |
| Monday | `/yt-plan` | Supply hours, unfinished work and prior ideas. Choose a feasible VFX, Creative or Experience concept. |
| Before generating, optional | `/yt-script` | Explore alternate first lines. Give the winning line and duration to the storyboard. |
| Storyboard and generation | `/yt-shorts` | Use original mode for paired still and motion prompts, or extraction mode for an existing transcript. |
| Rough cut | `/yt-edit` | Supply timed captions for spoken edits. For a silent shot inspect the cut visually. |
| Packaging | `/yt-package` | Pair the title with an actual frame from the payoff or setup. |
| Metadata | `/yt-seo` | Refine the description and relevant search terms, then copy them back into the same record. |
| Long compilation only | `/yt-chapters` | Use on a later compilation with a timed transcript. Skip for the standalone Short. |
| After manual publication | `/yt-comment` | Triage real comments and draft replies for your review. |
| Once analytics exist | `/yt-retention` | Compare audience drops with shot boundaries. For a 15-second Short the tool’s 30-second hook window covers the whole video. Read the opening directly from the curve. For CLI timestamps use position as 0–100 percent and pass the actual duration. |
| After several uploads | `/yt-audit` | Use actual results to choose one change to test in next week’s plan. |

## Install

Paste this into Claude:

```
https://github.com/ibrahimafridi881-commits/youtube-agent-skill

Install this skill, then confirm /yt-script works.
```

Or do it yourself, in Claude Code:

```bash
git clone https://github.com/ibrahimafridi881-commits/youtube-agent-skill.git
cp -r youtube-agent-skill/skills/yt-* ~/.claude/skills/
```

Or as a plugin:

```
/plugin marketplace add ibrahimafridi881-commits/youtube-agent-skill
/plugin install youtube-agent
```

Project-local instead of global: copy the same folders into your repo's `.claude/skills/`. No Claude
Code at all? Paste any single `SKILL.md` at the top of a chat and it runs as a mode. You lose the six
Python tools, which is most of the point of `/yt-script`, `/yt-retention` and `/yt-edit`, but the
rest works.

Then spend ten minutes on [`templates/voice.md`](templates/voice.md). Copy it to
`~/.claude/youtube/voice.md` and fill it in, or send Claude three of your own videos and say "write
my voice.md from these". Every skill reads that file. It matters more here than anywhere else,
because you have to say the words out loud.

## The eleven

| command | what it does |
| --- | --- |
| `/yt-script` | One idea into a script. Five hooks off [21 formulas](skills/yt-script/hooks.json), scored, then the spoken script with the retention beats marked. |
| `/yt-package` | Title and thumbnail as one pairing, linted for truncation, duplication and vagueness. |
| `/yt-edit` | A transcript into an edit decision list: dead air, filler cues, retakes, with timecodes. |
| `/yt-comment` | The comment section triaged into four piles, then replies in your voice. Says which one to pin. |
| `/yt-plan` | A week that fits the hours you actually have. Original Shorts or a mixed-format week. |
| `/yt-viral` | What is working in your niche, ranked by multiple over each channel's own median. |
| `/yt-retention` | Your retention export read properly: hook leak, the cliffs, the slide, and what to change. |
| `/yt-shorts` | Original cinematic Shorts from a brief, or standalone moments extracted from a long video. |
| `/yt-seo` | The description, the tags that are worth having, and the three queries this should win. |
| `/yt-chapters` | Chapters from a transcript, validated against YouTube's own rules so they render. |
| `/yt-audit` | The whole channel, ending in ONE fix rather than twenty. |

## The six tools

Every one of these runs on a clean Python 3 with no dependencies. They are the reason the skills are
not just prompts.

```bash
python3 skills/yt-script/hookscore.py --hook "one line"        # 5-property hook panel
python3 skills/yt-package/title.py --title "..." --thumb "..." # title + thumbnail linter
python3 skills/yt-edit/deadair.py transcript.srt               # edit decision list
python3 skills/yt-chapters/chapters.py transcript.srt          # validated chapters
python3 skills/yt-retention/retention.py retention.csv         # where they left, and why
python3 skills/yt-viral/swipe.py collected.json --min 2.0      # outliers by own-channel multiple
```

## The fine print

The part most packs leave out.

**It does not publish.** YouTube's Data API would allow it with your own OAuth, which makes this
pack different from the LinkedIn and Instagram ones, where posting is not available at all. It is
still not built here: every skill ends in a block you copy and a question — ship it, or change it?
Anything that claims to run your channel unattended should be read with that distinction in mind.

**`hookscore.py` is a heuristic, not a predictor.** The panel was built and calibrated against 74
real short-form hooks (the first 15 seconds of auto-captions, top-8 and bottom-8 by views across
five channels). It separates deliberately bad hooks from real ones well. It separates a given
creator's hits from their own misses barely at all. A low score is a reason to look again; a high
score is not a promise.

**The formula classifier is about the words, not the result.** When `/yt-viral` says a title used
The Statistic, that is a judgement about the title you can see, not a claim about why the video got
its views.

**`/yt-viral` reads, it does not scrape.** Public listings only. It never logs in as you and never
touches your credentials.

**Tags barely matter** and this pack says so instead of selling you a tag generator.

**Nothing invents a number.** If a skill wants a figure it does not have, it asks you for it or
writes the line without it.

## Licence

MIT. Use it, change it, ship it.
