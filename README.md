# GitHub Copilot Instruction Files

## Overview

This collection contains user-level instructions for GitHub Copilot. The files guide coding, security, accessibility, and collaboration behaviour across projects. They apply in supported chat and agent sessions, not to inline code completions as you type.

## Contents

Each instruction file uses frontmatter to describe when it applies. The `applyTo` field is a file-matching pattern, and `description` explains the tasks for which an instruction is relevant.

| File | Applies to | What it covers |
| --- | --- | --- |
| [copilot.instructions.md](copilot.instructions.md) | All files (`**`) | General guidance, precedence, collaboration, security, and writing conventions; points to the other instructions. |
| [coding-standards.instructions.md](coding-standards.instructions.md) | Common source, markup, style, configuration, and script files | Naming, renaming, capitalization, types, function size, lookup maps, and formatting. |
| [secure-coding.instructions.md](secure-coding.instructions.md) | Code, configuration, scripts, markup, and infrastructure files | Threat-aware design, defensive coding, self-review, and severity-based security fixes. |
| [accessibility.instructions.md](accessibility.instructions.md) | User interfaces and user-facing content across code, markup, documents, graphics, and translations | Ontario accessibility requirements and practical guidance for semantics, keyboard access, focus, forms, colour, contrast, motion, and content. |
| [typescript.instructions.md](typescript.instructions.md) | TypeScript and JavaScript files | Strict equality, explicit and precise types, and consistent syntax. |
| [java.instructions.md](java.instructions.md) | Java files | Avoids raw types, sets field naming rules, and uses maps for lookup data. |
| [stylesheets.instructions.md](stylesheets.instructions.md) | Cascading Style Sheets (CSS) and Sass (`.css` and `.scss`) | Standard features, formatting, vendor prefixes, and class naming. |
| [instruction-files.instructions.md](instruction-files.instructions.md) | Instruction, prompt, agent, and skill files | Focused wording, lean always-on instructions, and maintainable customization files. |

The global file also sets the collection's core rules: resolve instruction conflicts, honour project conventions, verify facts, use Canadian English, define abbreviations, and ask before running terminal commands. Read the individual files for the full requirements.

## Requirements

- A GitHub Copilot client that supports user-level instructions, such as the Copilot harness in Visual Studio Code (VS Code) or GitHub Copilot command-line interface (CLI).
- No runtime, package, or build dependencies. These are Markdown files.
- The user-level destination is `~/.copilot/instructions/`. These files are local to the machine and do not automatically sync between computers.
- The [accessibility-audit skill](../github-copilot-global-skills/accessibility-audit/SKILL.md) adds the detailed audit workflow referenced by `accessibility.instructions.md`; install that skill separately to use the complete workflow.

## Installation

Run the commands for your operating system from the root of this repository. Keep all filenames unchanged because the global instructions refer to the other files by name.

### Windows PowerShell

```powershell
$copilotRoot = Join-Path $HOME '.copilot'
$instructionDestination = Join-Path $copilotRoot 'instructions'
New-Item -ItemType Directory -Force -Path $instructionDestination | Out-Null
Copy-Item -Path '.\github-copilot-global-instructions\*.instructions.md' -Destination $instructionDestination -Force
```

### macOS and Linux

```bash
instruction_destination="$HOME/.copilot/instructions"
mkdir -p "$instruction_destination"
cp -f github-copilot-global-instructions/*.instructions.md "$instruction_destination/"
```

If GitHub Copilot CLI uses a non-default `COPILOT_HOME`, install the files under that directory's `instructions/` folder for the CLI to find them. Visual Studio Code may use a separately configured location. The commands overwrite files with matching names, so review any local edits first.

## Usage

Start a new Copilot chat or CLI session after installation or updates. The global `copilot.instructions.md` has `applyTo: "**"`; other files apply according to their file patterns and task descriptions. The agent includes relevant instructions when working on matching files or tasks. Instructions guide the model and do not guarantee a particular result.

The global instructions also establish these key behaviours:

- Resolve conflicts in order: safety, security, and legal requirements; the current user prompt; project instructions and skills; these global instructions; then language and tool defaults.
- Follow project conventions where required by the codebase or its technology.
- Do not run terminal commands without the user's explicit permission.
- Verify facts, ask when intent is unclear, and follow skills relevant to the task.
- Use Canadian English, define abbreviations, and fix critical and high-severity security findings before presenting code.

## Verification

- **VS Code:** Run **Chat: Open Customizations** from the Command Palette, select Instructions, and confirm the files appear. After a response, inspect **References** when available to see which files Copilot used.
- **Copilot CLI:** Run `/instructions` to list the instruction files discovered in the current session.

If files are missing, confirm the selected harness and user location. In VS Code, check that `chat.instructionsFilesLocations` includes `~/.copilot/instructions`. In the CLI, check whether `COPILOT_HOME` points to a different folder.

## Update and Uninstall

To update, copy the newer `*.instructions.md` files over the installed copies. Compare the source and destination folders and remove old copies manually if a file was renamed or removed; Copilot may discover every instruction file in the folder. Preserve any local edits you want to keep.

To uninstall, remove only this collection's instruction files from `~/.copilot/instructions/`. Review the folder first and retain any instructions added or edited independently. If Copilot CLI uses a custom `COPILOT_HOME`, use that directory's `instructions/` folder.

## Customization

Edit the copied Markdown files to tailor their guidance. Keep filenames stable where another instruction refers to them. New files should use the `*.instructions.md` suffix and valid frontmatter. Use `applyTo` to target files and `description` to describe relevant tasks. Narrow broad instructions when they conflict with a project's established conventions.

## Folder Layout

```text
github-copilot-global-instructions/
|-- accessibility.instructions.md
|-- coding-standards.instructions.md
|-- copilot.instructions.md
|-- instruction-files.instructions.md
|-- java.instructions.md
|-- secure-coding.instructions.md
|-- stylesheets.instructions.md
|-- typescript.instructions.md
|-- LICENSE
`-- README.md
```

## Licence

This collection is dedicated to the public domain under Creative Commons Zero (CC0) 1.0 Universal. See [LICENSE](LICENSE) for the full terms.

## Further Reading

- [VS Code: Use custom instructions](https://code.visualstudio.com/docs/agent-customization/custom-instructions)
- [VS Code: Custom instructions reference](https://code.visualstudio.com/docs/agents/reference/custom-instructions-reference)
- [GitHub Copilot CLI: Add custom instructions](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-custom-instructions)
- [Support for different types of custom instructions](https://docs.github.com/en/copilot/reference/custom-instructions-support)
