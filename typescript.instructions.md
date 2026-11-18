---
description: Apply type-safe, idiomatic TypeScript and JavaScript practices.
applyTo: "**/*.{ts,tsx,mts,cts,js,jsx,mjs,cjs}"
---

# TypeScript and JavaScript

- Use strict equality (`===`, `!==`) in preference to coercive equality.
- Prefer template literals when interpolating values or combining strings.
- In TypeScript, prefer precise types. Avoid `any`; use a concrete type or `unknown` with explicit narrowing where the value is not yet known.
- Add explicit parameter and return types to exported APIs, public contracts, and important boundaries. Add annotations for complex or ambiguous declarations.
- Allow inference for obvious local variables and initialisers. Do not add redundant annotations solely to repeat what the compiler already knows.
- Use typed `Record<Key, Value>` or `Map<Key, Value>` for key-to-value lookups where appropriate.
- Follow domain and project conventions for object property names. Do not force UPPER_SNAKE_CASE for `as const` object keys.
- Use the project's TypeScript strictness settings and formatter. Do not weaken compiler options to avoid resolving a type error.
- In JavaScript files, follow applicable language and project conventions without adding TypeScript-only syntax.
- For styles embedded in components, also follow `stylesheets.instructions.md`.

Brace style when no project formatter defines another convention:

```typescript
if(isEligibleForRenewal)
{
	renewSubscription(customerAccount);
}
else
{
	scheduleRenewalReminder(customerAccount);
}
```
