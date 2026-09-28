# learn

[![video](assets/thumbnail.png)](https://www.youtube.com/watch?v=kzcI5F4tGiU)

My AI learning system from this video: [How I Use AI to Learn Things](https://www.youtube.com/watch?v=kzcI5F4tGiU).

This is a personal system I built for myself, shared as-is. Built as a pi configuration: the teaching philosophy encoded in a skill, a few small extensions, and agent definitions.

## What's in it

- `skills/teach/` — the philosophy and the process
- `skills/visualize/` — adds a correct, minimal diagram to a lesson when an idea is clearer as a picture
- `extensions/ask-user-question.ts` — the agent asks you questions through a UI popup
- `extensions/quiz.ts` — graded questions with instant feedback (✓/✗, correct answer, explanation)
- `extensions/md-log.ts` — link a markdown file to the session
- `extensions/visual-tools/` — tools for visualization subagents
- `agents/` — `researcher`, `svg-maker`, `mermaid-maker`: the subagents the system delegates to

## How a lesson works

1. **Start teaching quickly.** Set a concrete goal, then ask at most five opening questions, including review from previous lessons. Stop sooner when the next teaching step is clear. Later prerequisite gaps become short teaching opportunities.
2. **Teach, attempt, get feedback, apply.** Build connected understanding, then choose quizzes, explanations, predictions, exercises, debugging, or small projects to match the goal. Finish with a small unfamiliar application. Use flashcards selectively for facts worth recalling.
3. **Remember across sessions.** Save preferences separately from evidence of learning. The next lesson revisits useful earlier ideas without requiring another full examination.
4. **Adapt the challenge.** Start from clear, checked foundations with necessary assumptions stated. Offer hints or worked examples when stuck, increase challenge when ready, and make progress visible by returning to earlier difficulties.

The teaching skill directs this process; the extensions supply the interactions. Quizzes compare selections with the teacher's answer key, while explanations and practical work are assessed by the teacher.

## Install

This repo **is** a `.pi` directory. From your learning project's root:

```bash
git clone https://github.com/MartinOndejka/learn .pi
```

Then open pi in that directory. (Or copy the pieces you want into your existing project config.)

## Learning memory and personalization

When a teaching session begins, the teacher reads these files in the learning project's root and creates missing ones from the bundled empty templates:

```text
your-learning-project/
├── .pi/                 # This repo: shared teaching instructions and tools
└── .learning/
    ├── LEARNER.md        # Preferences you explicitly state
    └── PROGRESS.md       # Goals, observed attempts, help given, next review prompts
```

The teacher updates the record after meaningful learning evidence and at the end of a lesson. It distinguishes an independent explanation, an attempt with help, and recall in a later session; hearing an explanation does not establish mastery. Earlier subjects remain available for review when the current goal changes. This is ordinary Markdown managed by the teaching agent, with no separate database or background scheduler. See the [learning-state instructions](skills/teach/references/learning-state.md) for details.

Tell the teacher your preferences, or edit `.learning/LEARNER.md` directly. To change the general teaching method, edit [the teaching skill](skills/teach/SKILL.md). You can decline saving and continue with the conversation alone. If your learning project uses Git, add `.learning/` to that project's `.gitignore` unless you want to track your personal records; the ignore rule inside `.pi/` does not cover its sibling directory.

Session transcripts are optional and separate. Use `/md-log` only with a dedicated transcript file: linking it can replace existing contents. Never link it to `LEARNER.md` or `PROGRESS.md`.

## Requirements

- [pi](https://github.com/earendil-works/pi)
- A subagent implementation, so the system can spawn the researcher and the visual makers. Recommended: [pi-interactive-subagents](https://github.com/amosblomqvist/pi-interactive-subagents) (tmux only). With it, everything works out of the box. Any other implementation works too, but expect to adapt the agent definitions, e.g. `agents/researcher.md` lists `safe_bash` in its tools, which is specific to that extension.
- `ask-user-question` — use the copy bundled here. If your setup already has an `ask-user-question` extension, use **this** one in its place. Popups from different extensions serialize through a shared UI lock, which only works when it's the same implementation.

## Notes

You can run the system without subagents. The main session teaches and checks claims directly using available sources, calculations, or examples. Research delegation and generated visuals require the supporting agents and tools.

The original personal teaching philosophy remains the starting point; your preferences and learning history belong in `.learning/`, rather than in the shared skill.
