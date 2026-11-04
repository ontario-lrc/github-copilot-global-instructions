# GitHub Copilot Instruction Files

This repository holds user-level custom instruction files (`*.instructions.md`) for GitHub Copilot. They tell Copilot how to write code, handle security and accessibility, and communicate in chat and agent sessions in Visual Studio Code (VS Code) and the GitHub Copilot command-line interface (CLI). Once installed, they apply in every project you open. They do not affect the inline suggestions that appear as you type.

## Where They Go

1. Create your user-level Copilot instructions folder if it does not exist: `%USERPROFILE%\.copilot\instructions` on Windows, or `~/.copilot/instructions` on macOS and Linux.
2. Copy every `*.instructions.md` file from this repository into that folder.
3. Start a new VS Code chat or Copilot CLI session. Copilot CLI does not apply instruction changes to a session that is already running.

Copy the whole set and keep the file names unchanged, because the files refer to each other by name. If you already have files with the same names, copying replaces them.

On Windows, you can open the folder by pasting `%USERPROFILE%\.copilot\instructions` into the File Explorer address bar.

### Check That They Load

- **VS Code:** Run **Chat: Open Customizations** from the Command Palette, select **Instructions**, and confirm that the files are listed. After a chat response, expand **References** to see which files Copilot used.
- **Copilot CLI:** Run `/instructions` in a session to list the instruction files that Copilot found.

### Update

Copy the newer files over your existing copies. If a file is removed or renamed in this repository, delete your old copy, because Copilot picks up every `*.instructions.md` file in the folder.

### Notes

- In VS Code, the `chat.instructionsFilesLocations` setting includes `~/.copilot/instructions` by default. If the files do not appear, check that this entry has not been removed or set to `false`.
- If you set the `COPILOT_HOME` environment variable, Copilot CLI reads the `instructions` folder inside that location instead.
- VS Code Settings Sync does not copy this folder, so repeat these steps on each computer.
- According to GitHub's [support matrix](https://docs.github.com/en/copilot/reference/custom-instructions-support), Copilot in Eclipse, Visual Studio, and Xcode supports only repository-level instruction files, so it does not read this folder.
- `accessibility.instructions.md` refers to the `accessibility-audit` skill for audits, reviews, and legal citations. The skill is not part of this repository; Copilot reads personal skills from `~/.copilot/skills/`. Without the skill, the file's rules still apply.

## What They Do

Each file begins with frontmatter that controls when Copilot uses it:

- `applyTo` is a glob pattern. Copilot adds the file automatically when it works on a matching file.
- `description` states when the file is relevant. In VS Code, the agent can also load the file on demand when the description matches the task.

| File | Applies to | What it does |
| --- | --- | --- |
| [copilot.instructions.md](copilot.instructions.md) | All files | Sets the global rules listed below and points Copilot to the other files. |
| [coding-standards.instructions.md](coding-standards.instructions.md) | Source, markup, stylesheet, configuration, and script files in common languages | Sets rules for identifier names, renaming, and capitalization, and requires lookup maps instead of `switch` statements, explicit types, small functions, Allman braces, and tab indentation. |
| [secure-coding.instructions.md](secure-coding.instructions.md) | Code, markup, configuration, script, and infrastructure files, including `Dockerfile*` and `.env*` | Sets a security workflow of threat-aware design, self-review, and severity-based fixes, plus technology-specific and defensive-coding rules. |
| [accessibility.instructions.md](accessibility.instructions.md) | Markup, templates, stylesheets, source code in most languages, vector graphics, documents, and translation, message, and design-token files | Sets the legal baseline under the Accessibility for Ontarians with Disabilities Act, with Web Content Accessibility Guidelines 2.0 Level AA as the legal floor and criteria from the latest versions as labelled recommendations, plus rules for semantics, keyboard and focus, forms and errors, colour, contrast, motion, content, and conformance claims. |
| [typescript.instructions.md](typescript.instructions.md) | TypeScript and JavaScript files | Requires strict equality, template literals, explicit type annotations, and precise types instead of `any`. |
| [java.instructions.md](java.instructions.md) | Java files | Forbids raw types, names `final` fields in upper snake case, and uses `Map` for lookup maps. |
| [stylesheets.instructions.md](stylesheets.instructions.md) | Stylesheet files (`.scss` and `.css`) | Allows only standard features without vendor prefixes, unless the team approves an exception, and sets formatting and class-naming rules. |
| [instruction-files.instructions.md](instruction-files.instructions.md) | Instruction, prompt, agent, and skill files | Requires short, focused, precisely worded instruction files, lean always-on files, and no counts that go out of date. |

### Global Rules

`copilot.instructions.md` tells Copilot to:

- Resolve conflicts in this order: safety, security, and legal requirements; your current prompt; project instruction files and skills; these files; then language, framework, and tool defaults.
- Let external constraints, such as language syntax and framework requirements, override the spelling, naming, typing, and formatting rules, and follow established project conventions where consistency requires it.
- Never run a terminal command, including builds, tests, installs, Git commands, and file operations, without your explicit permission. Approving a plan that lists the commands counts as permission.
- Verify facts instead of assuming, and ask when your intent is unclear.
- Read and follow every skill whose description matches the task.
- Keep chat replies short without losing clarity. Say "normal mode" or "stop caveman" to get full prose.
- Fix every critical and high security finding before presenting code.
- Use Canadian English spelling.
- Define each abbreviation and acronym before its first use.
- Never begin a file with a blank line, or end a file with a blank line or final newline.
- Prefer delegating multi-step research to subagents, and pass these rules on to them.

## More Information

- [Use custom instructions in VS Code](https://code.visualstudio.com/docs/agent-customization/custom-instructions)
- [Adding custom instructions for GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-custom-instructions)
- [Support for different types of custom instructions](https://docs.github.com/en/copilot/reference/custom-instructions-support)
