---
description: Apply accessibility requirements to user-interface markup, component templates, stylesheets, and localisation resources. Use the accessibility-audit skill for audits, legal analysis, native interfaces, and documents.
applyTo: "**/*.{html,htm,xhtml,shtml,jsp,jspx,tag,tagx,gsp,ftl,ftlh,vm,mustache,hbs,handlebars,ejs,pug,jade,njk,liquid,twig,erb,haml,slim,jinja,jinja2,j2,gohtml,tmpl,xsl,xslt,cshtml,razor,vbhtml,aspx,ascx,master,php,phtml,vue,svelte,astro,mjml,tsx,jsx,css,scss,sass,less,styl,xaml,axaml,fxml,qml,ui,storyboard,xib,svg,resx,xlf,xliff,po,pot,arb,strings,stringsdict,jrxml},**/*.component.{ts,js},**/*{messages,Messages}*.properties,**/{i18n,l10n,locale,locales,lang,translations,tokens}/**/*.{json,yml,yaml,properties},**/res/**/*.xml"
---

# Accessibility

These rules apply to user interfaces and user-facing content across web, native, and document technologies. Automatic matching is deliberately limited to likely UI implementation files. For native applications, documents, graphics, broader audits, and legal citations, use the `accessibility-audit` skill or attach this instruction when relevant. Adapt each fix to the platform and existing project conventions.

## Legal baseline

- Apply the Accessibility for Ontarians with Disabilities Act, 2005 (AODA), and its Integrated Accessibility Standards Regulation, Ontario Regulation 191/11 (IASR), as the governing Ontario accessibility law.
- IASR section 14 requires applicable internet websites and web content, including web-based applications, to conform to WCAG 2.0 Level AA. Verify scope and any applicable exceptions before making a legal finding.
- Do not report WCAG 2.0 success criteria 1.2.4 Captions (Live) or 1.2.5 Audio Descriptions (Pre-recorded) as AODA non-compliance for designated public sector and large organisations where the permanent section 14 exclusion applies. State the exclusion when relevant.
- For the Government of Ontario and Legislative Assembly, section 14 also addresses intranet and extranet websites. Check the applicable IASR provisions and dates before relying on a specific obligation.
- Treat WCAG 2.0 AA as the AODA baseline, not an accessibility ceiling. Label later criteria accurately as recommendations unless another applicable standard makes them mandatory.
- Do not describe WCAG 2.1 or later criteria as AODA requirements merely because they are newer.
- For non-web interfaces and documents, use WCAG2ICT to interpret applicable WCAG 2.0 Level A and AA criteria. Confirm the applicable legal and organisational scope separately.

## Ontario Public Service Digital Accessibility Standard

The Ontario Public Service (OPS) Digital Accessibility Standard (ODAS), Government of Ontario Information Technology Standard (GO-ITS) 201PRS, is an OPS policy requirement, not legislation. The published standard prevails over this summary and is available through InsideOPS.

- Apply ODAS to websites, web applications, mobile applications, and web content developed, procured, managed, or supported by an Ontario ministry, including applicable vendor and procured-product work, across internet, intranet, and extranet environments.
- Do not automatically apply ODAS to designated public sector organisations or products the Government of Ontario cannot modify. Its application to provincial agencies is not universal. Determine scope from project evidence and ask when uncertain.
- For in-scope products, use WCAG 2.1 Level A and AA as the current ODAS floor, including WCAG2ICT interpretation where applicable, unless the published standard has since changed.
- Label post-WCAG 2.0 criteria as ODAS requirements only when the work is in ODAS scope. Do not label policy requirements as legislation.
- In scope, consider the OPS testing methodology across automated, manual, and assistive-technology testing. Report which tiers were performed and which remain.
- Tell the user when an OPS accessibility report, project checklist, InsideOPS/ontario.ca verification, or approved exception process may apply. An audit produced here does not replace an official OPS report or process.
- If a requirement appears impracticable, report the issue. Do not assume an exception is granted.

## Semantics and names

- Prefer native semantic elements and platform-native controls over custom roles or redundant Accessible Rich Internet Applications (ARIA) attributes.
- Keep each control's name, role, value, and state correct and programmatically exposed.
- Give every input and control an accessible name or label.
- Use meaningful landmarks and heading structure.
- Provide appropriate text alternatives for non-text content. Complex images such as charts, maps, and diagrams need an accessible equivalent or explanation.

## Keyboard and focus

- Make every action operable using the keyboard alone.
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

## Colour, contrast, motion, and content

- Never convey meaning or status by colour alone.
- Meet applicable contrast requirements and recheck contrast after colour changes.
- Respect reduced-motion preferences when animating.
- Use link text that describes the destination; avoid ambiguous phrases such as "click here".
- Do not rely only on visual location, such as "see the chart below", to identify content.

## Changes and claims

- Keep accessibility changes focused. Avoid unrelated architecture, business-logic, or visual changes.
- Make recommendations specific and connect them to an actionable change.
- Never introduce a security regression. Preserve framework output sanitisation and do not insert unsanitised user-controlled data into markup.
- Do not claim legal compliance or certification, including "AODA certified" or "WCAG certified". State the evaluation performed and identify any required manual or assistive-technology testing that remains.
