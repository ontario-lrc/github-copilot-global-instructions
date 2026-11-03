---
description: Use when writing, changing, or reviewing source code, templates, stylesheets, configuration, or scripts in any language. Covers identifier naming, renaming, capitalization, lookup maps, type safety, function size, braces, and indentation.
applyTo: "**/*.{ts,tsx,mts,cts,js,jsx,mjs,cjs,java,kt,kts,groovy,gradle,cs,py,go,rs,php,rb,swift,c,cc,cpp,h,hpp,html,scss,css,sql,json,jsonc,xml,yml,yaml,toml,ps1,psm1,sh,bash,zsh,bat,cmd}"
---

# Coding Standards

These rules yield to external constraints and established project conventions, as the global instructions describe.

## Identifier Names

- Use complete, descriptive words for every programmer-chosen identifier, including variables, functions, methods, parameters, properties, keys, classes, interfaces, types, records, stylesheet class names, constants, enum members, database aliases in application code, and test names.
- Choose names that clearly communicate the identifier's purpose and meaning in its context.
- Prefer `customerAccount` over `custAcct`, `calculateDistance` over `calcDist`, `initialReportCount` over `initRptCnt`, `configurationSettings` over `config`, `authenticationRequest` over `authReq`, `previousValue` over `prevVal`, and `maximumRetryCount` over `maxRetries`.
- Prefer `employeeIdentificationNumber` over `empId` when the longer name improves clarity in that context.

### Abbreviations in identifiers

Use an abbreviation or acronym in an identifier, even a widely recognized one, only when its meaning is defined before first use and at least one of these applies:

- An external constraint requires it.
- It is the official name of a protocol, standard, technology, or externally defined concept, such as `API`, `CSS`, `DAO`, `DNS`, `DTO`, `HTML`, `HTTP`, `HTTPS`, `ID`, `IP`, `JNDI`, `JSON`, `SQL`, `SSE`, `SSL`, `TCP`, `TLS`, `UI`, `URI`, `URL`, `UUID`, or `XML`.
- It follows an established project, language, or framework convention already in widespread, consistent use.

Even then, prefer the complete term when it remains readable and practical.

### Single-letter names

- Do not use single-letter variable, parameter, or property names when a descriptive name can be used. Prefer `currentDate` over `d`, `customer` over `c`, `index` over `i`, `key` over `k`, `horizontalPosition` over `x`, `verticalPosition` over `y`, and `value` or a more domain-specific name over `v`.
- Use a more domain-specific name whenever possible. Prefer `customerIdentifier` over `id` when several identifiers are present, `orderIndex` over `index` when multiple collections are involved, `invoiceTotal` over `value` for an invoice total, and `configurationKey` over `key` for a configuration setting.
- Retain a conventional short name only when an external interface, language syntax, mathematical notation, or an established project convention that materially improves readability requires it. Do not use this exception merely for typing convenience.

### Generic names

- Avoid generic placeholder names, such as `data`, `info`, `item`, `object`, `obj`, `output`, `result`, `temp`, `thing`, `value`, and `val`, when a more specific, context-appropriate name exists.
- Prefer `customerRecords` over `data`, `validationOutcome` over `result`, `pendingInvoice` over `item`, `temporaryFilePath` over `temp`, `requestPayload` over `object`, `calculatedTaxAmount` over `value`, `employeeDetails` over `info`, and `serializedResponse` over `output`.
- A generic name may be acceptable when its meaning is already precise and unambiguous within a narrowly scoped abstraction, such as `value` and `key` in a reusable collection utility.

### Collections and Boolean values

- Use plural names for collections and singular names for their elements, such as `customerAccounts` and `customerAccount`, or `validationErrors` and `validationError`.
- Name Boolean identifiers so their `true` or `false` meaning is immediately clear, such as `isEnabled`, `hasPermission`, `canSubmitRequest`, `shouldRetryOperation`, and `wasSuccessfullyProcessed`.
- Avoid unclear Boolean names, such as `flag`, `status`, `check`, or `enabledValue`.

## Renaming Existing Identifiers

These rules cover renames made to satisfy these instructions, including Canadian English spelling, expanded abbreviations, and naming or capitalization style.

- Apply these conventions to all new identifiers and to identifiers already being renamed for functional or design reasons.
- Correct unclear local identifiers when the change is small, safe, and directly related to the requested work.
- Preserve existing public interfaces, serialized names, database fields, configuration keys, and external contracts unless a change is explicitly authorized.
- Do not bulk-rename existing identifiers, or rename them solely to change spelling or expand abbreviations, without team consent.
- Do not create large diffs solely to enforce naming preferences. Keep naming improvements within the requested scope unless broader cleanup has been approved.

Before a spelling, abbreviation, or broad naming rename:

1. Determine the identifier's complete intended meaning, including whether any abbreviation in it has conflicting definitions.
2. Determine whether it is externally visible or part of a public interface, serialized contract, database schema, configuration format, external integration, or compatibility boundary.
3. Identify all affected files, references, consumers, tests, integrations, and generated artefacts, and any potential breaking changes.
4. Obtain team consent when the rename is broad, compatibility-sensitive, or primarily stylistic.
5. For a broad rename, explain the expected benefits and risks, and add or update tests needed to confirm that behaviour remains unchanged.

When a pull request includes spelling or abbreviation changes, or substantial naming changes, add a short note to its description that:

- Summarizes the changes and any identifiers that were renamed.
- Defines affected abbreviations or acronyms and identifies any ambiguous meanings discovered.
- States whether public interfaces, compatibility boundaries, or consumers are affected.
- Records team consent when the change required approval.

## Capitalization

Apply these conventions consistently to all new or renamed programmer-chosen identifiers.

- Use camel case (`camelCase`) for variables, parameters, functions, methods, properties, object keys, local fields, non-constant members, and every other identifier that is not a type, constant, final field, constant object key, or enum member. Begin with a lowercase letter, capitalize the first letter of each subsequent word, and do not use underscores or hyphens. Examples: `customerAccount`, `calculateOutstandingBalance`, and `maximumRetryCount` as a mutable variable.
- Use upper snake case (`UPPER_SNAKE_CASE`), with words separated by underscores, for constants, final fields, constant object keys, and enum members, such as `MAXIMUM_RETRY_COUNT` and `DEFAULT_PAGE_SIZE`.
- Use Pascal case (`PascalCase`) for classes, interfaces, records, enumerations, and type aliases, such as `CustomerAccount`, `ValidationOutcome`, and `OrderRepository`.
- For acronyms inside identifiers, such as `customerId` or `customerID`, and `apiResponse` or `APIResponse`, follow the language and project convention and use one style consistently.

## Lookup Maps Instead of Switch Statements

- Avoid `switch` statements in new or modified code.
- Prefer a lookup map when logic maps discrete keys to fixed values, configuration objects, functions or handlers, commands or operations, factories, strategies, formatters, validators, or other predictable actions.
- Use the language's map, dictionary, or associative collection, or an equivalent lookup structure.
- Lookup maps make each key-to-value or key-to-action relationship explicit, reduce repetitive branching, keep mapping logic declarative, make new mappings easier to add, improve testability, and avoid large or frequently growing conditional blocks.

## Type Safety

- Use explicit type annotations for every programmer-declared variable, parameter, property, field, and return value, even where the language could infer the type.
- Types must make the code's data structures, contracts, nullability, and expected values clear without requiring the reader to infer them from an implementation or initializer.
- Use the most precise practical type, and never reach for a permissive escape hatch when a precise type can be declared.
- Where an external constraint forbids an annotation or fixes a signature, follow the constraint.

## Small, Focused Functions

These rules apply to every programmer-defined executable unit, including functions, methods, constructors, factory methods, callbacks, handlers, and test helpers.

- Write small, focused functions that each perform one clearly defined task.
- A function must have one primary responsibility and one clear reason to change, and its name, inputs, output, and implementation must describe a cohesive operation.
- If a function can only be described accurately by joining unrelated responsibilities with the word "and," split them into separate functions. For example, do not create one function that validates a request, displays validation errors, saves a record, and sends a notification.
- Keep functions short enough to understand at a glance. As a guideline, a function should not contain more than roughly 20 to 30 statements of logic; when it grows beyond that, extract cohesive sub-tasks into well-named functions.
- Favour pure, side-effect-free helper functions that accept inputs and return outputs, because they are inherently reusable and testable.
- When a block of logic could reasonably be reused elsewhere, even if it is currently used only once, extract it into a well-named function so that future callers can use it without duplication.
- Do not extract so aggressively that a reader must navigate many trivially small functions to follow a single operation. Keep the level of abstraction consistent within a module and use judgement.

## Formatting

These rules apply to all new or modified source code, including configuration files, templates containing source code, test files, and build and automation scripts, where the language supports them.

- Use Allman-style braces for every brace-delimited construct in every language, including classes, functions, control statements, exception-handling blocks, object literals, type declarations, namespace and module blocks, and stylesheet rule blocks.
- Place each opening brace (`{`) on its own line, aligned with the beginning of the preceding statement, declaration, or selector.
- Place each closing brace (`}`) on its own line, at the same indentation level as the construct that opened the block.
- Use one tab per indentation level, and never mix tabs and spaces for indentation. Use spaces only where the file format requires them.
- Do not reformat generated code, vendored source code, minified files, third-party code, or externally controlled files unless explicitly requested.
