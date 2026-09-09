# e2a Launch Video

A ~55s product launch film for **e2a**, built with [HyperFrames](https://hyperframes.heygen.com) and finished with voiceover and BGM.

The whole thing rides on one idea: **giving your AI agent a real email address is really giving it an identity.** Your agent is a new teammate, but it has no address and can't reach anyone. Once e2a gives it one, it can handle your outbound work, and you stay in control.

**Final cut:** [`renders/e2a Launch.mp4`](renders/)

---

## The Story

```
Intro    Meet your new agent.
Hook     You've got outbound work to hand off (customers, orders, meetings, vendors).
Pain     It can think and draft, but it can't reach anyone. It has no address
         (the only teammate on the roster without an email).
Reveal   e2a gives it a real address: agent@agents.e2a.dev. Identity, granted.
Work     It gets the work done, one business line at a time, each a real email thread:
         Support / Stripe, Scheduling / Google Meet, Commerce / Amazon, Reception / Slack.
Trust    Sending to 2,400 customers? It's HELD until you tap Approve.
Close    "Your agent doesn't need another dashboard. It needs an address." + one-line install.
Brand    e2a. Give your agent an address.
```

The core metaphor is **email address = identity**, not email = a communication feature.

---

# Video Production Workflow

## Video Editing Basics for Developers

For developers working with video for the first time, it helps to think of a video as a sequence of coordinated visual, textual, and audio layers:

- **A-roll** is the primary footage: the main presenter, interview, screen recording, or central narrative.
- **B-roll** is supporting footage inserted over or between A-roll to illustrate a point, establish context, add visual variety, or hide an edit.
- **Script** defines the message, narrative structure, and pacing. It is the source of truth for what the video needs to communicate.
- **Shots** are the individual visual units of a video. A shot can be product footage, a screen recording, a close-up, an interface state, or an animated graphic.
- **Captions** turn spoken words into on-screen text. They improve clarity, accessibility, and retention, especially when a video is watched without sound.
- **Audio** includes voiceover, dialogue, background music (BGM), and sound effects. It controls rhythm and emotional tone as much as the visuals do.
- **Motion design** gives information movement and emphasis. Common examples include titles flying in, cards expanding, data appearing, code being highlighted, infographics changing states, and animated transitions between scenes.

This workflow treats creative direction as the foundation of every video. B-roll, motion design, transitions, and music should all support a clear idea rather than compensate for a weak one.

## 1. Define the Storyboard

Creative direction is the most important part of the process. I work iteratively with GPT to develop and refine the concept until the narrative, pacing, and visual direction are clear. At this stage, we define the storyboard and shot list, including the purpose of each scene and its required B-roll.

## 2. Produce the Assets

### 2.1 Establish the Mode

First, I define a visual **Mode** based on the video's purpose, audience, and desired aesthetic. This establishes the visual language for the project: mood, typography, color, composition, motion, and overall style.

For reference-driven work, I can use HyperFrames' web-to-video skills to help an agent analyze a source video or website and extract its visual style and artistic direction.

### 2.2 Capture Product References

I ask an agent to capture screenshots from the product's official website. These references help the video stay faithful to the product's identity, including its fonts, logo usage, theme, and tone of voice.

### 2.3 Iterate on Clips

Each clip is refined through repeated review and revision. This can include adjusting the design, adding or improving motion, and redesigning transitions so the sequence feels intentional and cohesive.

### 2.4 Render

Once the clips and transitions are approved, I render the video.

### 2.5 Final Edit in CapCut

Finally, I bring the rendered video into CapCut to add background music and make fine editorial adjustments, such as timing, rhythm, and small cuts.

---

## Tooling: Remotion vs HyperFrames

These two aren't competitors, they're a division of labor.

**Remotion is powerful, but heavy to tweak locally.** It can produce genuinely cinematic shots, but when you just want to adjust one small piece of motion, the change is heavy: you often end up touching React components and recompiling the whole thing. That makes it a great fit for **orchestration and master control.**

**HyperFrames is direct to tweak, but not built for master control.** A frame is just a bit of HTML plus GSAP, so editing motion is immediate and seek-safe, exactly what you want when you're polishing. But it's not the tool for sequencing an entire film. That makes it a great fit for **making a single shot look better.**

### A workflow that uses both

If the goal is a reusable, long-term video production system (topic → script → shots → captions → visuals → export):

| Layer | Tool | Job |
| --- | --- | --- |
| **Orchestration** | **Remotion** | How the whole video flows: A-roll / B-roll, captions, audio, shots, timeline, master control. |
| **Per-shot polish** | **HyperFrames** | How one segment looks: a single shot, its motion, and B-roll, made premium. |

HyperFrames pairs well with the **`auto-motion` skill**, which splits motion shots into standalone projects so you can tune one segment without disturbing the rest. In short: **Remotion sets the skeleton and rhythm; HyperFrames polishes every bone.**

---

## How this cut was built (HyperFrames)

```
STORYBOARD.md          the shot plan (one beat per frame, with transition + duration)
SCRIPT.md              the locked voiceover
    |
compositions/frames/   hand-written HTML + GSAP per frame (single seek-safe timeline)
    |
audio.mjs              local Kokoro TTS for voiceover + duration sync
assemble-index.mjs     assembles index.html (frames + voice track)
transitions.mjs        injects cinematic seams (zoom-through / blur-crossfade / push-slide)
    |
hyperframes render     -> renders/*.mp4
    |
CapCut                 add BGM, final edit, export
```

---

## Design notes

- **Committed palette** (no clashing-color card grids): warm paper `#faf7f2`, deep canopy green `#2b4033`, a small set of harmonized category accents (green / blue / gold / plum), and electric lime `#d3fb52` as scarce voltage.
- **Type:** Fraunces (display), Inter (body), JetBrains Mono (addresses / terminal).
- **Recurring motif:** the address `agent@agents.e2a.dev` runs through the whole film, from an empty `????`, to typed-on and live, to a signature on every action.
- Use cases are shown **one business at a time, full screen** (not crammed into a single dashboard), with an oversized macOS cursor for the Approve tap.

---

## Repo layout

```
renders/e2a Launch.mp4     the final film
STORYBOARD.md / SCRIPT.md  shot plan + voiceover
frame.md                   the design system (palette / type / components)
compositions/frames/       the per-frame HTML (00-intro ... 07-brand)
assets/fonts/              brand fonts (woff2)
capture/                   brand tokens + screenshots captured from e2a.dev
index.html                 the assembled master composition
```
