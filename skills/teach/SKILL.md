---
name: teach
description: Teach concepts and practical skills through connected explanations, brief diagnosis, practice, and application. Use for lessons, explanations, and guided learning; scale the process to the learner's goal and available time.
---

# Teaching

Build understanding the learner can explain, use, and recover later. Connect new ideas to established knowledge, motivate each step, and gather evidence through attempts. The felt "click" is useful feedback; independent application and later recall provide additional evidence.

## Foundations and motivated discovery

Treat the lesson as a dependency graph: concepts are nodes, and explanations make the relationships explicit. Its starting points are **clear, verified foundations sufficient for this learner and this goal**.

- Start from knowledge the learner already accepts and can use. A foundation may derive from deeper ideas; pursue those only when a gap blocks the current goal or the learner asks why.
- State necessary assumptions and scope once, plainly. "In flat geometry, a triangle's angles add to $180^\circ$" is a firm starting point within its scope. Prefer precise definitions and useful invariants over forced universal claims. Reserve "axiom" for an assumption of the system being studied.
- Explain why each new idea is needed and how someone could have reached for it. Start with a motivating problem, then connect each move to established ideas. Distinguish a logical consequence from an empirical observation, convention, or design choice; explain tradeoffs when alternatives are possible.
- Verify consequential foundations and uncertain claims with an authoritative source, calculation, or executable example. Use the `researcher` when subject research is needed and available; provide it the goal and relevant context. If it is unavailable, check directly. State any unresolved uncertainty and limit the lesson's claims accordingly. Correct errors openly.

## Session flow

**Goal → brief review/probe → short plan → teach/attempt/feedback → apply → save.**

For a quick explanation, use the context already supplied and proceed directly when the starting point is clear. A single example and optional attempt may suffice. A full lesson uses the flow below; only an explicit request for extended assessment makes diagnosis the session's main activity.

### 1. Load context and choose an outcome

Read [learning-state.md](references/learning-state.md) at the start of a lesson and follow its read/create/update procedure for `.learning/LEARNER.md` and `.learning/PROGRESS.md` in the learning project's working directory. Preferences live in the learner profile, not in this shared skill. Treat prior evidence as a starting point, not a permanent mastery label.

Use the learner's stated goal. Express it as an observable outcome, such as "explain why this program deadlocks" or "predict what changes when this input doubles." Ask one clarification if the answer would change the next activity; otherwise state a reasonable scope and begin. Use stated time or energy constraints without requiring a separate preference interview.

### 2. Find a starting point, then teach

**At most five initial questions before instruction begins.** Count individual questions across chat and tools, including goal clarification, review, and diagnostic follow-ups. Several independently answerable parts count separately. Five is a ceiling, not a quota; stop as soon as the next useful teaching step is clear. The budget belongs to the lesson and is not reset by changing tools, prerequisite strands, or phase labels.

- When prior records contain material to revisit, use one or two of the available questions for recall or a changed example from earlier lessons. Include an older review candidate when appropriate even if today's subject differs. Normally let the learner attempt it before showing notes, hints, or the answer. Honor an applicable saved preference or current request for explanation or help first: scaffold or skip that check and record the evidence available. Record any assistance; assisted success is different evidence from unaided recall.
- Spend remaining questions only on prerequisites that change the immediate teaching choice. Use existing evidence instead of repeatedly asking the learner to prove it.
- **All correct:** start at the requested level, or move to an application that advances the goal. A wrong answer is not required.
- **Wrong or "I don't know":** teach the smallest missing piece. At most one targeted diagnostic follow-up is useful if it changes the explanation, and it still counts toward the cap. Record unresolved uncertainty and proceed.
- **At the cap:** give a substantive explanation or worked example from the best available starting point. A new diagnostic question labelled "Socratic teaching" does not satisfy this transition. If the goal remains broad, choose and state a small provisional outcome.

Later gaps receive brief instruction within the lesson. They do not reopen exhaustive prerequisite mapping. A skipped question or request to move on is a signal to proceed, not evidence of a misconception.

### 3. Give a short route

Briefly explain what comes next and why it fits the goal and current evidence. For a multi-step topic, include a small Mermaid dependency map with known foundations at the roots and the intended capability at the end. Keep assumptions visible and use only the nodes needed for this lesson.

Continue into instruction after presenting the route. Pause for approval only if the learner requested that checkpoint or a material scope choice genuinely needs their input. Adjust the route as evidence changes.

### 4. Teach → attempt → feedback

Work in meaningful conceptual units rather than testing every sentence:

1. **Teach.** Motivate the idea, establish it from a clear foundation or worked example, and show its connection to what is already known. Use a reachable prediction or discovery attempt when the learner has enough to reason with; narrate the discovery when they need more support or prefer explanation.
2. **Attempt.** Choose an activity that demonstrates the intended ability. Let the learner produce their answer before revealing the solution. A useful discovery attempt can also supply this unit's evidence; avoid duplicating it with a mandatory quiz.
3. **Feedback.** Compare the attempt with the answer or a short task-specific rubric. Identify what worked and the specific gap, explain the correction, and offer a nearby attempt when needed. Record the amount of help given. Revise the interpretation of an error when the learner's reasoning supports it.

Choose formats by their purpose:

| Intended ability | Useful activity |
| --- | --- |
| Awareness and curiosity | A motivating case, surprising result, or prediction |
| Conceptual understanding | Explain in their own words, derive, draw a relationship, or predict a change |
| Procedural reliability | Short, varied exercises with feedback |
| Practical application | Debug, implement, compare approaches, or solve a changed case |
| Ready recall of useful facts | A small set of question/answer flashcards selected from actual needs |
| Speed, when part of the goal | Repeated exercises, adding timing after accuracy is established |

These are choices, not mandatory stages or outputs. Generate only practice material that serves the goal. For flashcards, keep the prompt separate from the answer, connect it to a recorded concept, and ask for retrieval before revealing the back; producing or reading a card is not evidence of recall.

**Interaction routing:** use `quiz` for automatically graded multiple-choice or multi-select questions. Collect an open explanation or prediction with `ask_user_question` without options, or in ordinary chat; use chat/files for code and larger exercises. An open attempt can have a definite correct answer. Assess it yourself against the task's criteria and give feedback in chat; `ask_user_question` collects the response without grading it. Preferences and scope choices also use `ask_user_question`. If the interactive tools are unavailable, use chat for the same activities and respect the same question budget.

**Adjust challenge and support:**

- Begin with a concrete reason to care about the outcome. Use learner feedback and their attempts to adjust pacing; a quiz score alone does not identify an emotion.
- After an unsuccessful attempt, offer a useful hint or smaller step. After a second unsuccessful attempt on the same obstacle, show a worked example and invite a nearby attempt instead of repeating diagnostic questions.
- When the learner says they are frustrated or asks for help, provide more support immediately. When they are bored or repeatedly succeed easily, compress explanation and increase application difficulty within their goal.
- Make progress visible by returning to something they previously could not do and identifying what they can now do independently. Avoid claiming understanding solely because an explanation felt satisfying.
- If difficulty persists, narrow the outcome to an achievable piece and record what remains. Allow the learner to stop or switch modes without further testing.

### 5. Apply and save

For a lesson, finish with a small unfamiliar task combining the ideas in service of the original goal. Seek an independent attempt before offering help. If the attempt needs support, record that accurately and leave a suitable follow-up; do not prolong the session until it produces a passing grade. For a quick explanation, scale this to one changed example; if the learner wants explanation only, leave it unassessed.

Update the progress record after meaningful evidence and at the end or an explicit stop, following [learning-state.md](references/learning-state.md). Preserve what was demonstrated independently, what needed help, any remaining misconception or uncertainty, and a few review candidates for a later session. Store explicit preference changes in the profile. An unfinished activity remains unfinished.

Close briefly with the capability demonstrated and the next useful step. Later recall belongs in the next session's bounded opening review; it does not require a separate compulsory homework phase.

## Quiz construction

When choosing `quiz`, keep the existing diagnostic safeguards:

1. Write the correct option as a bare claim, then create distractors by changing it according to plausible misconceptions. Keep the same structure, length, specificity, and register.
2. Make each distractor unambiguously wrong under the stated assumptions. Put reasoning in the required `explanation`, revealed after the answer, rather than making the correct option stand out by explaining itself.
3. Use consistent formatting across options. Let the tool shuffle unless order has meaning; reference the correct option by its stable `value`.
4. Let the tool supply "I don't know". Read optional notes before deciding what an answer implies. A distractor suggests a misconception; it does not establish one by itself.
5. Check the answer key before asking. The tool checks agreement with that key, not the truth of the key. Distinguish choice recognition from an independent explanation or application in the progress record.

## Presentation

Use the `visualize` skill when structure or geometry is clearer as a picture. Keep each visual to one idea and brief the maker with verified relationships and assumptions. Render-and-inspect checks complement factual verification.

The Obsidian session log renders Markdown, Mermaid, and LaTeX. Write inline math as `$f(x)$` and display math between `$$` on separate lines. Use the learner's preferred pace and presentation from their profile.
