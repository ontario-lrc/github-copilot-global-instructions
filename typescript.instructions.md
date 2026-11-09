---
description: Use when writing, changing, or reviewing TypeScript or JavaScript code.
applyTo: "**/*.{ts,tsx,mts,cts,js,jsx,mjs,cjs}"
---

# TypeScript and JavaScript

- Always use strict equality (`===`) and strict inequality (`!==`) instead of loose equality (`==`) and loose inequality (`!=`). Loose operators perform implicit type coercion, which can conceal type mismatches and introduce unexpected behaviour.
- Prefer template literals, which use backticks and `${...}` interpolation, over string concatenation when embedding expressions or constructing strings from multiple parts.
- In TypeScript, write `const recordCount: number = 0;` rather than `const recordCount = 0;`, and `private readonly customerAccounts: CustomerAccount[] = [];` rather than relying on inference.
- Annotate every return type, including `void` and `Promise<void>`.
- Never use `any`. Use a precise type, a union, a generic type parameter, or `unknown` followed by explicit narrowing.
- Name `as const` object keys in upper snake case, such as `LARGE: "large"`.
- Implement lookup maps with `Record<KeyType, ValueType>` or `Map<KeyType, ValueType>`.
- For styles embedded in components, also follow `stylesheets.instructions.md`.

Brace style:

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
