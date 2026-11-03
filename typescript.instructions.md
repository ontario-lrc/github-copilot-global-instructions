---
description: Use when writing, changing, or reviewing stylesheets, including styles embedded in templates or components.
applyTo: "**/*.{scss,css}"
---

# Stylesheets

These rules cover all Sassy Cascading Style Sheets (SCSS) and Cascading Style Sheets (CSS), including styles embedded in templates or components, test stylesheets, and generated stylesheet source maintained by the project.

## Standards Compliance

- Use only selectors, properties, values, functions, at-rules, pseudo-classes, and pseudo-elements defined by official World Wide Web Consortium specifications.
- Do not use experimental, proprietary, deprecated, browser-specific, or non-standard features unless their use is explicitly required and approved by the team. This includes vendor-prefixed selectors, pseudo-classes, and pseudo-elements, such as `::-webkit-scrollbar`, `::-webkit-scrollbar-track`, `::-webkit-scrollbar-thumb`, and `::-moz-range-thumb`.
- When a standardized equivalent exists, such as `scrollbar-width` or `scrollbar-color`, use it instead. Otherwise, omit the styling and rely on browser defaults.

## Formatting

- Place each property declaration on its own line.
- End every declaration with a semicolon, including the final declaration in a block.
- Use double quotes for string values.
- Leave one blank line between sibling rule blocks.
- Do not leave a blank line before the first nested child of a block.
- Place each selector in a comma-separated selector list on its own line.
- Use camel case for class names unless an established naming convention requires another format.

Brace style:

```scss
.customer-summary-panel
{
	display: flex;
	gap: 1rem;

	&:hover
	{
		opacity: 0.8;
	}
}
```
