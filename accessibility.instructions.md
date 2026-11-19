---
description: Mandatory accessibility requirements for user interfaces, application components, documentation, and user-facing content. Apply whenever relevant content is generated or modified, even when accessibility is not mentioned.
applyTo: "**/*.{md,mdx,adoc,rst,html,htm,xhtml,shtml,jsp,jspx,tag,tagx,gsp,ftl,ftlh,vm,mustache,hbs,handlebars,ejs,pug,jade,njk,liquid,twig,erb,haml,slim,jinja,jinja2,j2,gohtml,tmpl,xsl,xslt,cshtml,razor,vbhtml,aspx,ascx,master,php,phtml,vue,svelte,astro,mjml,tsx,jsx,css,scss,sass,less,styl,xaml,axaml,fxml,qml,ui,storyboard,xib,svg,resx,xlf,xliff,po,pot,arb,strings,stringsdict,jrxml},**/src/app/**/*.ts,**/*.component.{ts,js},**/*{messages,Messages}*.properties,**/{i18n,l10n,locale,locales,lang,translations,tokens}/**/*.{json,yml,yaml,properties},**/res/**/*.xml"
---

# Accessibility

Accessibility is a mandatory engineering requirement for every generated or modified deliverable. This instruction provides the concise, automatically applied baseline for likely user-interface source files and text documentation. Apply the same principle to other artefacts, including native interfaces, office documents, PDFs, spreadsheets, presentations, graphics, diagrams, and reports. Use the `accessibility-audit` skill for detailed procedures, non-web formats, substantial reviews, and legal or standards analysis.

## Mandatory policy

- Do not wait for the user to request accessibility. Do not offer an accessibility opt-out, and do not treat silence or a request to skip accessibility as permission to create an inaccessible deliverable.
- Design and implement accessibility from the beginning. Accessibility is a completion and acceptance requirement, not an optional post-development enhancement.
- Every newly generated or modified deliverable must be accessible for its intended audience using the applicable requirements for its format and use.
- Correct accessibility defects introduced by the task before reporting the work as complete. Do not silently expand the task to remediate unrelated pre-existing content; identify relevant pre-existing barriers and report them separately unless remediation is within scope.
- If an intended output cannot be made accessible in the requested format, do not present it as a completed acceptable deliverable. Provide an accessible equivalent or explain the blocking limitation. Do not claim that a legal or organisational exception exists unless it has been formally established.
- Make the generated accessibility report, test evidence, diagrams, and other supporting artefacts accessible as well.

## Determine applicable requirements

- Identify the relevant jurisdiction, organisation, product or service, audience, delivery channel, contractual commitments, and organisational policies before classifying a requirement as legal or mandatory policy.
- Apply the Accessibility for Ontarians with Disabilities Act, 2005 (AODA), and the Integrated Accessibility Standards Regulation, Ontario Regulation 191/11 (IASR), where the organisation and content fall within their statutory scope. Do not assume AODA applicability solely because a developer, user, or supplier is located in Ontario.
- For in-scope web content, verify the current IASR provisions, covered organisation category, control over the content, publication date, exceptions, and relevant deadlines before asserting a legal obligation. IASR section 14 establishes a WCAG 2.0 Level AA requirement for applicable internet websites and web content. Do not describe later WCAG success criteria as AODA statutory requirements merely because they are newer.
- Account for the permanent section 14 exclusion for WCAG 2.0 success criteria 1.2.4 Captions (Live) and 1.2.5 Audio Descriptions (Pre-recorded) where it applies. Verify the scope and state the exclusion when relevant.
- For Government of Ontario and Legislative Assembly intranet or extranet content, verify the applicable IASR provisions and dates. Do not generalise that obligation to other organisations.
- Apply the Ontario Public Service (OPS) Digital Accessibility Standard (ODAS) only when the product or service is within its scope. ODAS is an organisational policy standard, not legislation. Do not assume it universally applies to agencies, designated public sector organisations, or suppliers.
- Identify other applicable jurisdictional laws, regulations, technical standards, procurement requirements, contracts, and organisational policies. Where an organisational standard is stricter than a legal minimum, follow the organisational standard unless it conflicts with law.
- Where no project-specific web target is supplied, use WCAG 2.2 Level AA as the default engineering target. This is an internal quality baseline, not a claim that WCAG 2.2 is the statutory requirement under AODA. For native and document-based outputs, use the relevant platform requirements and applicable WCAG2ICT guidance where appropriate.
- If legal or organisational applicability cannot be established, state the uncertainty and avoid legal-compliance claims. Continue to apply the appropriate technical accessibility baseline.

## Interface semantics and names

- Prefer native semantic elements and platform-native controls over custom roles or redundant Accessible Rich Internet Applications (ARIA) attributes.
- Keep each control's name, role, value, and state correct and programmatically exposed.
- Give every input and control an accessible name or label.
- Use meaningful landmarks and a logical heading structure.
- Provide appropriate text alternatives for non-text content. Complex images such as charts, maps, and diagrams need an accessible equivalent, data representation, or explanation.

## Keyboard and focus

- Make every action operable using the keyboard alone where the platform supports keyboard interaction.
- Preserve logical focus order, visible focus, and avoid unexpected focus traps.
- Manage focus after route changes, dialogs, overlays, menus, expansion panels, and asynchronous updates.
- Modal dialogs must manage focus, close using Escape where expected, and return focus to the trigger when closed.
- Verify focus behaviour across Shadow DOM boundaries where applicable.

## Forms, errors, and status

- Programmatically identify required fields and communicate requirements visibly and to assistive technology.
- Provide labels and instructions; identify input errors in text.
- Make errors specific and explain how to correct them.
- Associate field errors and help text with their controls.
- For multi-field submission errors, provide an error summary linked to invalid fields and move focus appropriately.
- Use live regions only when they improve announcement without excessive interruption.

## Documents, spreadsheets, presentations, and visual content

- Use semantic heading styles, meaningful document titles, correct language metadata, descriptive links, logical reading order, and accessible tables.
- Provide meaningful alternative text for informative images. Mark decorative imagery appropriately. Do not put essential information only in an image.
- For charts and diagrams, provide a concise text summary and an accessible data or structural equivalent where the visual encodes material information.
- For spreadsheets, use descriptive worksheet names, clear header rows, meaningful table structures, logical reading order, and labels that do not depend on colour alone.
- For presentations, provide meaningful slide titles, logical object reading order, sufficient contrast, alternatives for visual information, and captions or transcripts for relevant audio/video.
- For PDFs and office documents, preserve document structure, tags, headings, tables, links, language, and reading order in the generated output. Do not assume that visual appearance alone makes a document accessible.

## Colour, contrast, motion, and content

- Never convey meaning or status by colour alone.
- Meet the applicable contrast requirements and recheck contrast after colour changes.
- Respect reduced-motion preferences when animating.
- Use link text that describes the destination; avoid ambiguous phrases such as "click here".
- Do not rely only on visual location, such as "see the chart below", to identify content.
- Use clear, direct language appropriate to the audience without removing information needed to understand the content.

## Changes, verification, and claims

- Keep accessibility changes focused. Avoid unrelated architecture, business-logic, or visual changes.
- Make recommendations specific and connect them to an actionable change.
- Verify accessibility at a level proportionate to the artefact and risk. Use automated checks as an initial aid, followed by applicable manual checks such as keyboard operation, focus order, screen-reader behaviour, document reading order, and alternative text.
- Do not claim that automated scans alone establish conformance. Report the checks actually performed and any manual or assistive-technology verification that remains.
- Never claim legal compliance or certification, including "AODA certified" or "WCAG certified". State the evaluation performed and identify the requirements and verification limits.
- Never introduce a security regression. Preserve framework output sanitisation and do not insert unsanitised user-controlled data into markup.
