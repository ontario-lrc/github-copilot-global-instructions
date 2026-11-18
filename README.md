# GitHub Copilot Global Instructions

User-level instructions for GitHub Copilot in Visual Studio Code.

## Design

Keep `copilot.instructions.md` short because it applies to every task. Use scoped `*.instructions.md` files for language, file-type, or domain-specific rules. Use Agent Skills for repeatable multi-step procedures. Avoid duplicating the same rule in several files.

## Instruction inventory

| File | Scope |
|---|---|
| `copilot.instructions.md` | Global baseline and execution guardrails |
| `coding-standards.instructions.md` | General source-code conventions |
| `secure-coding.instructions.md` | Secure implementation and self-review |
| `accessibility.instructions.md` | UI accessibility and user-facing content |
| `typescript.instructions.md` | TypeScript and JavaScript |
| `java.instructions.md` | Java |
| `stylesheets.instructions.md` | CSS and Sass |
| `ontario-web-standard.instructions.md` | Government of Ontario Web Standard; attach manually only to an in-scope project |
| `instruction-files.instructions.md` | Authoring and maintaining instruction files |

## Automatic and manual application

Most files use `applyTo` patterns to load only for matching files. `accessibility.instructions.md` is deliberately limited to UI markup, component templates, stylesheets, and localisation resources. For native application interfaces, documents, and other surfaces, invoke the `accessibility-audit` skill or attach the instruction when relevant.

`ontario-web-standard.instructions.md` intentionally has no `applyTo` pattern. Attach it manually only when the project evidence shows that the Government of Ontario Web Standard applies. Do not load it automatically for all web projects.

## Installation

Copy `*.instructions.md` files into the personal Copilot instructions directory:

- Windows: `%USERPROFILE%\.copilot\instructions`
- macOS/Linux: `~/.copilot/instructions`

### Windows PowerShell

```powershell
$source = (Get-Location).Path
$destination = Join-Path $HOME '.copilot\instructions'
New-Item -ItemType Directory -Force -Path $destination | Out-Null
Get-ChildItem -LiteralPath $source -Filter '*.instructions.md' -File |
    Copy-Item -Destination $destination -Force
```

Do not copy this README into the instructions directory. Review local edits before overwriting matching files. `ontario-web-standard.instructions.md` must be attached manually for relevant tasks.

## Companion repositories

- [Global Agents](https://github.com/ontario-lrc/github-copilot-global-agents)
- [Global Skills](https://github.com/ontario-lrc/github-copilot-global-skills)
