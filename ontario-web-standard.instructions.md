---
description: Use only for a Government of Ontario website, web application, or web-content project that is within the scope of GO-ITS 100PRD.
---

# Government of Ontario Web Standard

Attach this instruction manually only when the project evidence establishes that the Government of Ontario Web Standard applies. It intentionally has no `applyTo` pattern because it must not load automatically for unrelated web projects.

These rules summarise version 3.0 of the Government of Ontario Information Technology Standard (GO-ITS) 100PRD Government of Ontario Web Standard. The published standard prevails. Verify each requirement against the current published standard before relying on it in a compliance statement:

https://www.ontario.ca/page/go-its-100prd-government-ontario-web-standard

## Scope

- Apply to Government of Ontario websites and web applications, on the internet or intranet and wherever hosted, including applicable third-party services and vendor work.
- The standard binds ministries, information and information technology clusters, adjudicative and advisory agencies, and other agencies bound by the applicable Governance and Management of Information Technology Directive or memorandum of understanding.
- Do not apply it to back-office and administrative interfaces such as human resources, financial administration, or content-management contribution interfaces.
- Determine scope from project evidence, including domain, documentation, organisation, hosting, and service integration. Ask the user when evidence does not settle a decision that changes the work.
- Apply requirements to the work in scope and report unrelated gaps rather than fixing them without approval.
- Read "must" as a requirement and "should" as a recommendation. Record material reasons when a recommendation is not followed.
- Treat requirements arising from legislation, such as accessibility, French-language services, and privacy legislation, as legal requirements.
- Do not state that a site complies with the standard as a whole. Report the specific requirements assessed and any outstanding approval or review.

## Accessibility and design

- Follow `accessibility.instructions.md`. Ontario ministries must also follow the OPS Digital Accessibility Standard where it applies.
- Use the Ontario Design System (ODS) for public-facing digital services delivered by Ontario ministries and provincial agencies whose services are integrated with ontario.ca, including applicable procured products.
- ODS is not required by this standard for internal-facing websites or agencies whose services are not integrated with ontario.ca. Intranet sites must follow the applicable ministry communications guidance.
- Follow ODS guidance for navigation, images, and forms.

## Content and language

- Follow the Ontario.ca style guide. Use concise descriptive headings, plain language, active voice, and a reading level appropriate to the audience. Explain technical terms and abbreviations in context.
- Apply the relevant publication and metadata requirements, including ISBN requirements for applicable one-time publications.
- Do not amend Government website content for third-party platforms or services such as social media.
- Apply the French Language Services Act, 1990, and Ontario Regulation 544/22 to public-facing websites where required, including Active Offer and simultaneous English/French publication requirements. Intranet websites need not be bilingual under this standard.
- Language toggles must lead to equivalent content in the other language.
- Publish content in languages other than English or French in accessible PDF format where required by the standard.
- Include required copyright statements on public-facing non-HTML documents and link to the central copyright statement where applicable: https://www.ontario.ca/page/copyright-information.

## Titles, links, and documents

- Apply the applicable GO-ITS 400DTS metadata requirements.
- Give each page a unique, concise, descriptive `<title>` in the required `document title | website name` format and length. Follow the standard's Ontario and ministry naming rules.
- Use descriptive links consistent with accessibility, ODS, the Ontario.ca style guide, and the Web Content Editing Guide.
- Identify the format and file size for links to non-HTML files and provide equivalent alternate-language or alternate-format destinations.
- Create redirects when important URLs change during a relaunch or content reorganisation.
- Refer to websites by fully qualified domain name, not IP address or server name.
- Follow the standard's rules for proprietary formats and Office documents on public-facing and intranet sites.
- Where a PDF is necessary for legal or security reasons, make it as accessible and secure as technically possible.

## Multimedia and navigation

- Make public-facing images, video, audio, and applications accessible and compliant with language requirements.
- Follow the standard's Ontario image and video sourcing guidance, including central Government of Ontario channels and asset libraries where applicable.
- Provide navigable site structure, breadcrumbs, and search for sites exceeding the standard's content threshold. Include related content where useful.
- Provide useful 404 pages and appropriate redirects or moved-content explanations for relocated resources.

## Search and analytics

- Follow the standard's ontario.ca Search Service indexing, metadata, certificate, and crawlability requirements where applicable.
- Provide `sitemap.xml` and `robots.txt` where applicable.
- Present search results with the current query, useful refinement, accurate titles and descriptions, result counts, pagination information, and duplicate handling.
- Collect aggregate performance and traffic statistics for the purpose of improving the service. Do not identify individuals through analytics unless authorised by law, and do not reuse or share analytics for unrelated purposes.
- For ontario.ca websites, prefer the central Government analytics setup arranged with Cabinet Office Communications.

## Privacy and security

- Display a Notice of Collection at or before every point where personal information is collected. State the legal authority, purpose, and contact information for questions.
- Link to the central Ontario privacy statement: https://www.ontario.ca/page/privacy-statement.
- Collect only personal information necessary for the service. Mark non-essential fields as optional unless collection is otherwise authorised or explicitly consented to.
- Do not use personal information in logs to identify individuals unless legislation authorises it. Anonymise or aggregate analytics data.
- Retain personal information only as long as required and follow applicable disposal and recordkeeping requirements.
- Design sessions, cookies, tokens, and state management to prevent unauthorised access to personal information.
- Follow applicable HTTPS, certificate, web application firewall, cryptography, web application security, and vulnerability management standards.
- Follow `secure-coding.instructions.md`.

## Forms, feedback, log-in, and subscriptions

- Provide a feedback mechanism on public-facing websites and list alternative channels where available. Feedback forms must also meet applicable accessibility and common service requirements.
- Use anti-spam measures where email addresses are published.
- Log-in pages must identify the service, explain registration, and provide help and credential-recovery guidance.
- Subscription pages must provide a Notice of Collection and plain-language service description. Protect subscriber information, restrict access, and use it only for the stated purpose.
- Do not use tracking mechanisms that reveal individual subscriber actions or preferences unless authorised and necessary. Subscription emails must provide an unsubscribe option and a feedback link.

## Compliance and approvals

- Confirm any approval, exception, security, privacy, architecture, analytics, or publication decision required by the current published standard and the responsible Government of Ontario authority.
- Do not infer that an approval or exception exists. Record the evidence and status.
- Report the specific requirements reviewed, evidence, gaps, and decisions still required. Do not certify overall compliance.
