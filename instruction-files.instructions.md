---
description: Use when creating or editing instruction, prompt, agent, or skill files.
applyTo: "**/*.{instructions,prompt,agent}.md,**/SKILL.md,**/AGENTS.md,**/CLAUDE.md,**/copilot-instructions.md"
---

# Instruction Files

These rules cover repository instruction files, scoped `.instructions.md` files, prompt files, agent definitions, and skill files.

- Write each instruction as a short, self-contained, imperative statement. Long files are more likely to be partially ignored.
- Keep the wording precise. Retain articles, conditions, and requirement words, such as must, should, prefer, unless, and where practical, because they set each rule's strength. Do not use the terse chat-reply style in instruction files.
- Keep each file focused on one topic. Put language- or topic-specific rules in their own file, with an `applyTo` pattern and a `description` that says when to use it.
- Keep always-loaded files, such as those with `applyTo: "**"`, lean, because they cost tokens on every request. Move rules that only some tasks need into scoped files.
- Never record counts or totals that drift as a side effect of ordinary development, such as file, lint-violation, test, or line counts. They go out of date without anyone noticing, and agents keep relying on them after they are wrong.
- Record instead the stable fact that the figure supports, such as "both source trees are live" rather than how many files each tree contains, or the command or location that produces the current figure when the figure itself matters.
- You may record counts that change only through a deliberate design decision, such as the number of build modules or pipeline stages.
