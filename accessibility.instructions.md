---
description: Use when creating, changing, or reviewing anything that people see, hear, or operate, including user interfaces on any framework or platform, markup, templates, stylesheets, user-facing text and messages, translations, documents, and graphics. Covers the Ontario accessibility legal baseline, the Ontario Public Service (OPS) Digital Accessibility Standard (ODAS) for Ontario ministries, native semantics, names and labels, keyboard and focus, forms and errors, colour, contrast, motion, content, and conformance claims.
applyTo: "**/*.{html,htm,xhtml,shtml,jsp,jspx,tag,tagx,gsp,ftl,ftlh,vm,mustache,hbs,handlebars,ejs,pug,jade,njk,liquid,twig,erb,haml,slim,jinja,jinja2,j2,gohtml,tmpl,xsl,xslt,cshtml,razor,vbhtml,aspx,ascx,master,php,phtml,vue,svelte,astro,mjml,ts,tsx,mts,cts,js,jsx,mjs,cjs,css,scss,sass,less,styl,java,kt,swift,m,mm,dart,cs,vb,py,rb,go,rs,c,cc,cpp,h,hpp,xaml,axaml,fxml,qml,ui,storyboard,xib,svg,md,mdx,rst,adoc,resx,xlf,xliff,po,pot,arb,strings,stringsdict,jrxml},**/res/**/*.xml,**/*{messages,Messages}*.properties,**/{i18n,l10n,locale,locales,lang,translations,tokens}/**/*.{json,yml,yaml,properties}"
---

# Accessibility

These rules apply to every user interface and all user-facing content on any technology: web frameworks, design-system component libraries, server-rendered templates, plain markup, stylesheets, and scripts, native mobile and desktop software, kiosks, and documents. Adapt each fix to the markup, styling, and scripting model that the codebase already uses. For accessibility audits, reviews, and legal citations, also use the `accessibility-audit` skill.

## Legal Baseline

Treat these rules as legal requirements, which rank first in the global precedence order.

- Apply the Accessibility for Ontarians with Disabilities Act, 2005 (AODA), and its Integrated Accessibility Standards Regulation, Ontario Regulation 191/11 (IASR), as the governing law.
- Make internet websites and web content, including web-based applications, conform to Web Content Accessibility Guidelines (WCAG) 2.0 Level AA, as IASR section 14 requires. The regulation defines WCAG as the World Wide Web Consortium (W3C) WCAG 2.0 Recommendation of December 2008.
- Never report success criteria 1.2.4 Captions (Live) and 1.2.5 Audio Descriptions (Pre-recorded) as AODA non-compliance for designated public sector and large organizations, because both are permanently excluded from their section 14 obligation. Note the exclusion explicitly.
- For the Government of Ontario, which includes every ministry, and the Legislative Assembly, section 14(1) also covers intranet websites, which section 14(7) defines to include extranet websites, and section 14(3) has required both of those success criteria since January 1, 2020.
- Treat WCAG 2.0 Level AA as the legal floor, not the ceiling. You may recommend Level AA success criteria from the latest WCAG versions as best practice, such as 1.4.10 Reflow, 1.4.11 Non-text Contrast, 1.4.13 Content on Hover or Focus, 2.4.11 Focus Not Obscured, 2.5.8 Target Size, and 4.1.3 Status Messages. For work in the scope of the Ontario Public Service (OPS) Digital Accessibility Standard (ODAS), which the next section describes, the WCAG 2.1 criteria among these examples are requirements, not enhancements.
- Label each requirement as "AODA legal requirement (WCAG 2.0 AA)", as "ODAS requirement (WCAG 2.1 AA)" for work in ODAS scope, or as "recommended enhancement (latest WCAG versions)". Never present a success criterion added after WCAG 2.0 as an AODA legal requirement.
- When a change meets only the WCAG 2.0 floor but a stronger, low-cost accessibility outcome is available, recommend the stronger outcome, and cite AODA section 38 as the reason: when provisions conflict, the one that gives the highest level of accessibility prevails. The standards also do not replace or limit duties under the Human Rights Code (AODA section 3 and IASR section 1(2)).
- For non-web user interfaces, such as native mobile, desktop, and kiosk software and documents, apply the same WCAG 2.0 Level A and AA success criteria as interpreted by the W3C guidance on applying WCAG to non-web information and communications technologies (WCAG2ICT).

## OPS Digital Accessibility Standard

The Ontario Public Service (OPS) Digital Accessibility Standard (ODAS), Government of Ontario Information Technology Standard (GO-ITS) 201PRS, has been mandatory for Ontario ministries since September 1, 2024. It is policy, not legislation, so never label its requirements as legal requirements. It is published on InsideOPS, the OPS intranet, behind an OPS sign-in, and the published text prevails over this summary, so ask the user to confirm a requirement against it when that requirement decides the outcome.

- Apply ODAS to every website, web application, mobile application, and item of web content that an Ontario ministry develops, procures, manages, or supports, on the internet, an intranet, or an extranet, including work by vendors and procured products, such as software-as-a-service and commercial off-the-shelf products. Web content includes text, images, forms, documents, video, and audio.
- ODAS does not apply to designated public sector organizations or to products that the Government of Ontario cannot modify, directly or through a contract, and it only recommends equivalent requirements for provincial agencies. Decide from project evidence whether the work is in scope, and ask the user when the evidence does not settle it.
- Make products in scope accessible by design throughout the product lifecycle. ODAS requires "WCAG 2.1, meeting both Level A and AA criteria, or the most recent WCAG requirements", and its footnote says that it will move to WCAG 2.2 Level A and AA once those requirements are ratified in Ontario. Until the published standard changes, treat WCAG 2.1 Level A and AA as the ODAS floor, applied through WCAG2ICT for mobile applications and documents.
- Label the success criteria that WCAG 2.1 added at Level A and AA, such as 1.4.10 Reflow, 1.4.11 Non-text Contrast, 1.4.13 Content on Hover or Focus, and 4.1.3 Status Messages, as "ODAS requirement (WCAG 2.1 AA)", and label those that WCAG 2.2 added as recommended enhancements.
- When ODAS and the IASR differ, apply the requirement that gives the highest level of accessibility.
- Test every product in scope with all three tiers of the OPS testing methodology: automated, manual, and assistive-technology testing. Testing should happen throughout the lifecycle and should use the OPS testing tools, and, where possible, it must include people of varying abilities, needs, experiences, and backgrounds using different devices. When reporting, state which tiers the work covered and which remain.
- A completed accessibility report, which should use the OPS template, is required for each website, web application, and mobile application in scope that is built or procured, gets a major release, upgrade, or enhancement, or has any change that affects its user interface. A report is valid for two years. When the work triggers one, tell the user, because an audit that you produce does not replace it.
- Delivery teams that go through a cluster or enterprise information technology (IT) governance process must implement the guidance in the Digital Accessibility IT Project Checklist, which needs an OPS network connection. When the work is part of such a project, remind the user.
- Only an approved Web Accessibility Compliance Exception, submitted through the OPS exception process, waives an ODAS requirement. Until one is approved, report the requirement as unmet, and tell the user when a requirement seems impracticable.
- Before content is published on InsideOPS or ontario.ca, its author must verify its accessibility with the OPS standard verification process. When you prepare such content, remind the user.

## Semantics and Names

- Prefer native semantic elements and platform-native controls over Accessible Rich Internet Applications (ARIA) attributes and custom roles. Add an explicit role, state, or property only when no native element conveys it, and never use redundant or conflicting semantics.
- Keep the name, role, value, and state of every control correct. In non-web software, expose them through the platform accessibility application programming interface (API).
- Give every input and control a programmatic name or label.
- Mark page regions with semantic landmarks, such as `header`, `nav`, `main`, and `footer`, and structure content with meaningful headings.
- Provide a text alternative for every image and other non-text content. For a complex image, such as a chart, map, or diagram, provide a text summary or an accessible alternative.

## Keyboard and Focus

- Make every action possible with the keyboard alone.
- Keep a logical focus order and a visible focus indicator, and never create an unexpected focus trap.
- Manage focus for dynamic user interfaces on every framework and surface, including client-side route changes, dialogs and overlays, menus, expansion panels, and asynchronously loaded content.
- In a modal dialog, trap focus inside the dialog, close it with the Escape key, and return focus to the triggering control when it closes.
- For web components that render inside a shadow Document Object Model (DOM), verify that focus trapping and focus restoration work across the shadow boundary.

## Forms, Errors, and Status Messages

- Mark each required field programmatically, such as with the `required` attribute or a validator, show the requirement visibly near the field's label, and make sure screen readers announce it.
- Provide labels or instructions for input (success criterion 3.3.2), and identify each input error in text (success criterion 3.3.1).
- Make each error message specific, and say how to fix the error.
- Associate each field-level message with its field, such as through `aria-describedby`.
- When a submission can fail on several fields, show an error summary that links to each invalid field, and move focus to the summary heading when the submission fails.
- Use live regions sparingly and intentionally.

## Colour, Contrast, and Motion

- Never convey information or status by colour alone (success criterion 1.4.1).
- Meet the minimum contrast requirement (success criterion 1.4.3), and verify contrast after every colour change.
- Respect the user's reduced-motion preference, such as the `prefers-reduced-motion` media feature, when animating.

## Content

- Write link text that describes the destination, and avoid "click here".
- Never use a visual location, such as "see the chart below", as the only way to identify content.

## Changes and Claims

- Keep accessibility fixes minimal, and do not change unrelated architecture, business logic, or visual design unless an accessibility requirement needs it.
- Map every accessibility recommendation to a specific code change, and never give vague accessibility advice.
- Never introduce a security regression in an accessibility fix: never bypass the framework's built-in output sanitization or insert unsanitized, user-controlled data into the page, such as through raw markup insertion or `innerHTML`. Also follow `secure-coding.instructions.md`.
- Never claim legal compliance or certification, such as "AODA certified" or "WCAG certified". WCAG conformance requires human evaluation, so recommend a formal audit and state what still needs manual or assistive-technology testing.
