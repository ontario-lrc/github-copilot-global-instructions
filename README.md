# GitHub Copilot Global Instructions

Reusable user-level instructions for GitHub Copilot across projects.

## Design
Keep the always-applied `copilot.instructions.md` concise. Put language-, file-, or activity-specific rules in scoped `*.instructions.md` files with accurate `applyTo` patterns and descriptions. Avoid repeating detailed procedures that belong in Agent Skills.

The existing specialised instruction files for coding standards, secure coding, accessibility, Ontario web standards, TypeScript/JavaScript, Java, stylesheets, and instruction-file authoring should be retained. This refresh replaces only the global baseline file; it does not remove those topic-specific files.

## Instructions

| Instruction | Responsibility |
|---|---|
| copilot.instructions.md | Baseline behaviour and guardrails for all Copilot interactions |
| accessibility.instructions.md | Accessibility requirements, semantic markup, keyboard support, and inclusive UX guidance |
| coding-standards.instructions.md | Shared coding standards for maintainability, readability, and consistency |
| secure-coding.instructions.md | Security-focused coding practices, validation, and safe defaults |
| java.instructions.md | Java-specific conventions, tooling expectations, and implementation guidance |
| typescript.instructions.md | TypeScript and JavaScript standards, patterns, and quality expectations |
| stylesheets.instructions.md | CSS and stylesheet conventions for structure, maintainability, and browser compatibility |
| instruction-files.instructions.md | Authoring guidance for scoped instruction files, metadata, and applyTo patterns |

The repository keeps a concise baseline instruction set plus topic-specific instruction files that are applied only when relevant.

## Installation

Copy instruction files into the user-level Copilot instructions directory.

### Windows PowerShell
```powershell
$source = (Get-Location).Path
$destination = Join-Path $HOME '.copilot\instructions'
New-Item -ItemType Directory -Force -Path $destination | Out-Null
Get-ChildItem -LiteralPath $source -Filter '*.instructions.md' -File |
    Copy-Item -Destination $destination -Force
```

### macOS / Linux
```bash
destination="$HOME/.copilot/instructions"
mkdir -p "$destination"
find . -maxdepth 1 -type f -name '*.instructions.md' -exec cp -f {} "$destination/" \;
```

Review local changes before overwriting matching files. Do not delete topic-specific instruction files as part of this update.

## Companion repositories
- [Global Agents](https://github.com/ontario-lrc/github-copilot-global-agents)
- [Global Skills](https://github.com/ontario-lrc/github-copilot-global-skills)