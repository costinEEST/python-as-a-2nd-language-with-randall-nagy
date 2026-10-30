---
name: maintain-python-course-notes
description: Create, clean up, explain, and organize Markdown lesson notes in this Python as a Second Language repository, including REPL transcripts and the README lesson index. Use when adding or revising course-note Markdown files or updating their table-of-contents entry.
---

# Maintain Python Course Notes

Turn rough lesson notes, terminal captures, or Python REPL transcripts into
clear instructional Markdown while preserving what the learner actually tried.

## Lesson notes

- Inspect the README and existing lesson files before editing so the new note
  follows the repository's terminology and structure.
- Keep lessons as Markdown when they combine prose, commands, and output. Use a
  `.py` file only when the requested artifact is a runnable program rather than
  explanatory notes.
- Give each lesson a descriptive title and organize it into short sections that
  follow the order in which the concepts are introduced.
- Explain commands near the examples where the explanation is useful. Cover
  what each command is, what it does, why its output appears, and any
  easy-to-miss behavior. Do not merely reproduce a transcript.
- Preserve instructive mistakes from the original session when they reveal an
  important distinction. Clearly explain the correction. For example, commands
  entered at Python's `help>` prompt are not ordinary Python expressions.
- Remove incidental noise such as full build banners, editor messages, and
  exhaustive `dir()` output when it does not teach the lesson. Mention when
  output varies by Python version or environment.
- Prefer explanations suitable for a learner who already knows another
  programming language but is learning Python.

## Code fences

Choose the fence language based on the content:

- Use `pycon` for interactive Python sessions containing `>>>` prompts and
  their output.
- Use `python` for source code without prompts or captured output.
- Use `console` for shell commands and terminal output, including the command
  that starts Python.
- Use `text` for non-Python interactive prompts such as `help>`.

Do not tell the reader to type prompt characters such as `$`, `>>>`, or
`help>`.

## Python terminology and behavior

- Describe `=` as binding or reassigning a name to an object; avoid implying
  that Python variables are permanently restricted to one type.
- Explain built-ins such as `dir()`, `help()`, and `type()` in context.
- Distinguish passing a callable or type to `help()` from calling it. Note that
  a string passed to `help()` is interpreted as the name of a help topic.
- Introduce terms such as REPL and dunder names the first time they are useful,
  using plain language.

## README maintenance

Whenever a lesson note is added or renamed:

1. Add or update its entry in the README table of contents.
2. Keep every captured course topic as a simple bullet in course order.
3. For a topic whose Markdown file exists, make the topic title a relative
   Markdown link to that file.
4. Leave topics without a Markdown file as plain text. Do not add speculative
   links, lesson numbers, durations, status markers, table columns, or separate
   placeholders.

Keep general course and documentation links in the README's **Resources**
section, not mixed into the lesson table.

## Finishing checks

Review the rendered Markdown structure, verify all newly added relative links
resolve to real files, and run a whitespace/error check on the files changed.
Do not modify unrelated working-tree changes.
