---
description: Apply maintainable CSS and Sass conventions while respecting project browser support and build tooling.
applyTo: "**/*.{scss,css}"
---

# Stylesheets

These rules apply to CSS and Sass files maintained by the project, including component and test stylesheets. Follow the project's formatter, naming system, design tokens, and supported-browser policy first.

## Standards and compatibility

- Prefer standardised CSS features with established browser support for the project's target matrix.
- Use vendor-prefixed or browser-specific declarations only when required by the supported browsers or an approved design requirement. Prefer the project's compatibility tooling, such as Autoprefixer, where configured.
- Do not use deprecated or experimental features without a documented compatibility reason and project approval.
- Do not add browser-specific scrollbar or control styling merely for decoration. When native controls are preferable or support is inconsistent, preserve usable browser defaults.

## Formatting

- Put one declaration on each line and terminate declarations with semicolons.
- Use double quotes for string values.
- Leave one blank line between sibling rule blocks.
- Keep selector lists readable, with each selector on its own line.
- Follow the project's class naming convention. If none exists, use descriptive names and a consistent convention.
- Avoid unnecessary specificity, duplicated declarations, and unrelated restyling.

Brace style when no project formatter defines another convention:

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
