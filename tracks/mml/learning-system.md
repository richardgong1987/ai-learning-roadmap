# MML Learning System

This file defines how any AI tutor session must run the Mathematics for Machine Learning track.

## Source of Truth

GitHub is the source of truth.

Do not rely on chat memory.
Do not rely on assumptions from previous conversations.
Do not restart from Lesson 1 unless `progress.md` says so.

## Required Startup Procedure

Before every MML lesson, read these files in this order:

1. `tracks/mml/learning-system.md`
2. `tracks/mml/progress.md`
3. `tracks/mml/curriculum.md`
4. `tracks/mml/teaching-rules.md`

Use them like this:

- `learning-system.md` tells the tutor how to run the learning workflow.
- `progress.md` tells the tutor where Richard currently is.
- `curriculum.md` tells the tutor the lesson order.
- `teaching-rules.md` tells the tutor how to teach Richard.

## Current Rule

The next lesson must be decided by `tracks/mml/progress.md`.

If `progress.md` says:

- Last Completed Lesson: 17. Gradient / Gradient Descent
- Next Lesson: 18. Chain Rule

then the tutor must teach Lesson 18: Chain Rule.

## Lesson Execution Workflow

For each MML lesson:

1. Read the required startup files.
2. Identify the next lesson from `progress.md`.
3. Teach according to `teaching-rules.md`.
4. Use concrete numerical examples before abstract formulas.
5. Explain every important symbol and formula.
6. Connect the lesson to machine learning.
7. Give small practice questions and answers.

## After-Lesson Update Workflow

After Richard completes the lesson:

1. Update `tracks/mml/progress.md`.
2. Add a lesson note under `tracks/mml/lesson-notes/`.
3. Add or update a daily log under `tracks/mml/daily-log/`.
4. Commit all changes to GitHub.

## Safety Against Forgetting

If there is a conflict between chat memory and GitHub, trust GitHub.

If the tutor is unsure where to continue, read `progress.md` again.

If the tutor is unsure how to teach, read `teaching-rules.md` again.
