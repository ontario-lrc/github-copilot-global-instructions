---
description: Apply concise, language-neutral coding conventions for naming, type safety, control flow, and maintainability.
applyTo: "**/*.{ts,tsx,mts,cts,js,jsx,mjs,cjs,java,kt,kts,groovy,gradle,cs,py,go,rs,php,rb,swift,c,cc,cpp,h,hpp,html,scss,css,sql,json,jsonc,xml,yml,yaml,toml,ps1,psm1,sh,bash,zsh,bat,cmd}"
---

# Coding Standards

These are defaults. Preserve established project conventions, public contracts, external constraints, language idioms, and formatter output.

## Naming

- Use clear, descriptive names proportionate to their context. Prefer meaningful words over unexplained abbreviations.
- Retain conventional abbreviations and short names where they improve readability or are established by the language, framework, protocol, or project.
- Follow the language and project casing conventions. Common defaults are camelCase for variables and members, PascalCase for types, and UPPER_SNAKE_CASE for constants where customary.
- Do not rename public or widely used identifiers solely to impose a preference. Avoid broad rename churn.

## Types and collections

- Prefer precise types and safe handling of unknown or nullable data.
- Avoid unsafe escape hatches such as TypeScript `any` when a concrete type or `unknown` with narrowing is practical.
- Allow inference for obvious local values. Add explicit types at public/API boundaries and where inference is unclear or materially improves readability.
- Use typed maps or records for fixed key-to-value lookups. Choose the collection type that suits the operation and language.

## Control flow and functions

- Prefer straightforward, readable control flow. Use `switch` when it is the clearest construct; do not prohibit it categorically.
- Keep functions cohesive and focused. Extract logic when it improves comprehension, reuse, or testability, not to satisfy an arbitrary line or statement count.
- Avoid unnecessary abstractions, duplicated logic, hidden side effects, and unrelated refactoring.

## Formatting

- Follow the repository formatter and existing file style.
- Where no project convention exists, use Allman-style braces and tabs consistently with the examples in this repository.
- Do not reformat unrelated code merely to impose these defaults.
