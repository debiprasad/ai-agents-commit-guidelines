# AI Agent Instructions for Generating Git Commit Messages

Follow these rules strictly when generating Git commit messages.

---

## 1. Message Structure

A commit message must follow this format:

<subject line>

<body (optional)>

Rules:
- The first line is the **subject**.
- If a body is included, insert exactly **one blank line** between the subject and body.
- Do not add extra blank lines at the beginning or end.
- Do not use Markdown formatting, emojis, or decorative characters.

---

## 2. Subject Line Requirements

The subject line must:

1. Be written in **imperative mood**  
   - Correct: `Add validation for request ID`
   - Incorrect: `Added validation for request ID`
   - Test: It should complete the phrase  
     "If applied, this commit will <subject>"

2. Start with a capital letter.

3. Not end with a period.

4. Be concise:
   - Target: ≤ 50 characters
   - Hard maximum: 72 characters

5. Describe **what the change does**, not how it was implemented.

6. Reflect only the staged changes. Do not assume context beyond the diff.

Avoid:
- Past tense (Added, Fixed, Updated)
- Gerunds (Adding, Fixing)
- Vague summaries (Changes, Updates, Misc fixes)

---

## 3. Body Guidelines (Optional)

Include a body only when additional explanation is necessary.

If included:

- Insert exactly one blank line after the subject.
- Wrap all lines at ≤ 72 characters.
- Explain:
  - Why the change was made
  - What problem it solves
  - Any important context not obvious from the diff
- Avoid line-by-line implementation details.
- Use clear, complete sentences.
- Optionally include issue references at the end (e.g., `Fixes #123`).

---

## 4. Scope Rules

- Summarize only the staged changes.
- Keep commits atomic (one logical change per commit).
- Do not bundle unrelated concerns.
- Do not speculate about unstaged work.

---

## 5. Optional Conventional Commit Mode

If the repository uses conventional commits, format the subject as:

<type>: <imperative summary>

Where `<type>` is one of:
- feat
- fix
- docs
- style
- refactor
- test
- chore
- perf
- ci
- build

Rules:
- Keep the summary in imperative mood.
- Add exactly one space after the colon.
- Keep total subject length within limits.

Example:

fix: Prevent alert injection in URL field

Sanitize user-provided URLs before rendering in the Traffic
and Explore → Attack view. Previously unescaped values could
trigger browser alerts via injected event handlers.

---

## 6. Final Validation Checklist

Before producing the final commit message, verify:

- Subject ≤ 50 characters (preferably)
- Subject uses imperative mood
- Subject starts with a capital letter
- Subject has no trailing period
- Blank line exists if body exists
- Body lines wrap at ≤ 72 characters
- Body explains why, not how
- No Markdown, emojis, or unnecessary formatting
- No trailing whitespace
