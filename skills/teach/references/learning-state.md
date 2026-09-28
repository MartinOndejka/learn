# Learning state

Keep two small Markdown files in `<learning-project-cwd>/.learning/`, alongside the installed `.pi/` directory. Resolve the path from the project where the learner starts pi, not from this skill's location. These files are working memory for the teacher; the optional session transcript remains separate.

## Start a lesson

1. Read `.learning/LEARNER.md` and `.learning/PROGRESS.md` when present. Apply explicit preferences, inspect the current goal and next step, and select useful review candidates even if today's subject changes. For an unaided check, read saved answers privately and present only the review prompt before the learner attempts it. Follow the teaching skill's preference and support rules when a refresher is wanted first.
2. Unless the learner has declined saving, create each missing file from its matching template: [learner-template.md](../assets/learner-template.md) and [progress-template.md](../assets/progress-template.md). Create missing files only; preserve existing files and user-written content. Start with empty evidence, not assumptions about the learner. Briefly mention the location on first creation; no profile interview is required before teaching.
3. Use the progress record to choose one or two opening review questions within the teaching skill's total probing limit. Prioritize unresolved gaps and ideas previously attempted with help. If nothing useful is recorded, begin from today's goal. A new topic updates the current goal without discarding older concepts or pending reviews.

If saving is declined, make no learning-state writes, including initialization or a preference recording that refusal. Continue teaching using the conversation. If files cannot be read or written, explain the limitation briefly and continue; do not claim that progress was saved.

## What to record

`LEARNER.md` contains only preferences the learner explicitly states: desired pace, explanation style, use of hints, challenge, accessibility or format choices. Record the scope of temporary requests (for example, "today, show worked examples") so they do not become permanent defaults. An observed wrong answer, slow response, or successful exercise is not evidence of a preference or an emotion.

`PROGRESS.md` uses three sections:

- **Current goal:** the capability the learner wants, plus the next useful teaching step. Preserve unfinished goals in the relevant concept entries when the topic changes.
- **Concepts:** one entry per useful concept, with a stable, readable ID such as `networking/retransmission`; its associated goal; dated evidence; and remaining uncertainty or a specific misconception. Evidence states what the learner actually did, the outcome, and the assistance given. Distinguish encountering an explanation, explaining independently, applying with help, and recalling in a later session. These are observations, not a single mastery score.
- **Next session:** a short queue of concept IDs and concrete prompts, with a trigger such as `next session` or an agreed date. Save the prompt separately from its answer so it can be presented without revealing the solution. A later check should require recall or a changed example rather than recognition of the same options.

For each evidence entry, capture enough to choose the next activity: the task or question, a concise response/outcome summary, and cue history (`independent`, `options supplied`, `hint: …`, `worked example shown`, or another specific aid). A correct answer after help remains evidence of helped performance; a fresh successful attempt can add independent evidence. A task completed without further help after a refresher can demonstrate application, but cannot establish unaided delayed recall. A demonstrated misconception differs from an untested prerequisite or a possible slip: label uncertainty plainly.

Use actual ISO dates (`YYYY-MM-DD`) for observed work. If the next lesson's date is unknown, schedule a check for `next session`; do not invent a calendar date. Same-session success does not establish later retention. Without evidence, leave the capability unknown.

## Update and finish

Update incrementally after a meaningful attempt, correction, or explicit preference, and save a final checkpoint when the lesson ends or the learner asks to stop. Record partial work honestly; finish saving without extending the lesson with another assessment. At the checkpoint, preserve the current goal, next useful step, and a small set of review prompts.

Keep the files concise by updating existing concept entries. Retain the latest evidence and any earlier result needed to explain a misconception, assistance, or later recall; preserve other subjects and user notes. After a review, append its dated result and update or retire that prompt. Report what was saved briefly, without announcing mastery unsupported by the record.

Use ordinary file reads and targeted edits; no database or logging extension is needed. Never point `/md-log` at either learning-state file: linking the transcript logger can replace the target file's contents.
