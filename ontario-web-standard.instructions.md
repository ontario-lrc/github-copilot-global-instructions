---
description: Use when creating, changing, or reviewing a Government of Ontario website, web application, or web content, whether internet or intranet, including Ontario Public Service (OPS), ministry, agency, and vendor work. Covers the scope and requirements of the Government of Ontario Information Technology Standard (GO-ITS) 100PRD Government of Ontario Web Standard, including the Ontario Design System, French language, content, page titles and metadata, links, documents, multimedia, navigation, site search, analytics, privacy, security, forms, feedback, log-in screens, subscriptions, and required approvals.
applyTo: "**/*.{html,htm,xhtml,shtml,jsp,jspx,tag,tagx,gsp,ftl,ftlh,vm,mustache,hbs,handlebars,ejs,pug,jade,njk,liquid,twig,erb,haml,slim,jinja,jinja2,j2,gohtml,tmpl,xsl,xslt,cshtml,razor,vbhtml,aspx,ascx,master,php,phtml,vue,svelte,astro,mjml,ts,tsx,mts,cts,js,jsx,mjs,cjs,css,scss,sass,less,styl,resx,xlf,xliff,po,pot,arb},**/*{messages,Messages}*.properties,**/{i18n,l10n,locale,locales,lang,translations}/**/*.{json,yml,yaml,properties},**/sitemap*.xml,**/robots.txt"
---

# Government of Ontario Web Standard

These rules summarize version 3.0 of the Government of Ontario Information Technology Standard (GO-ITS) 100PRD Government of Ontario Web Standard, published at https://www.ontario.ca/page/go-its-100prd-government-ontario-web-standard. The published standard prevails over this summary. Verify a requirement against it before relying on that requirement in a compliance statement.

## Scope

- Apply these rules to Government of Ontario websites and web applications, both internet and intranet, wherever they are hosted, including third-party web services and work by vendors. Multi-jurisdictional sites must meet the whole standard, with a look and feel that the partners agree on.
- The standard binds ministries, information and information technology clusters, adjudicative and advisory agencies, and other agencies that use Ontario Public Service (OPS) information technology and are bound to it by the Governance and Management of Information Technology Directive or a memorandum of understanding.
- Do not apply these rules to back-office and administrative interfaces, such as human resources, financial administration, or content-management contribution interfaces.
- Decide from project evidence, such as the domain, the project documentation, or the use of the Ontario Design System (ODS), whether the work is in scope and whether the site is public-facing or internal. When the evidence does not settle a question that changes the work, ask the user.
- The standard is mandatory on a go-forward basis, at the next project development or procurement opportunity. Apply it to the work being done, and report other gaps that you notice instead of fixing them unasked.
- Read must as an absolute requirement. Read should as a recommendation that may be set aside only after its implications, such as for business functionality, security, and cost, are weighed and stated.
- Treat requirements that come from legislation, such as accessibility, French language services, and privacy legislation, as legal requirements, which rank first in the global precedence order.
- Never state that a website complies with the standard as a whole. State which requirements the work meets and which still need review or an approval from the last section.

## Accessibility and Design

- Follow `accessibility.instructions.md` on every website and web application, internet or intranet. Ontario ministries must also follow GO-ITS 201PRS OPS Digital Accessibility Standard; when one of its specific requirements matters, ask the user for it instead of inferring it.
- Use the ODS for every public-facing digital service delivered by an Ontario ministry, or by a provincial agency whose services are integrated with ontario.ca, including procured commercial off-the-shelf software and software-as-a-service products. To add it to an application, use the `add-ontario-design-system` skill.
- The ODS is not required for internal-facing websites or for agencies whose services are not integrated with ontario.ca. Intranet websites must follow the design elements and content design guidance of the ministry's communications branch.
- Follow the ODS guidance for navigation, images, and forms, including field labels, buttons, drop-down lists, input formatting, error messages, and live, pre-submission, and post-submission validation.

## Content and Language

- Make all website content follow the Ontario.ca style guide. Write short, descriptive headings and leads, use the active voice and a reading level that suits the audience, add a plain-language summary to technical pages and documents, and define technical terms, abbreviations, and acronyms in context, with a glossary and pronunciation guide where appropriate.
- Give each online format of a one-time publication, such as a report, budget, or plan, an International Standard Book Number.
- Never amend government website content for a third-party platform or service, such as social media.
- Make public-facing websites comply with the French Language Services Act, 1990, including Active Offer and the measures in Ontario Regulation 544/22. Publish all documents equally in English and French at the same time, and post a disclaimer on content that is available only in English. Intranet websites need not be bilingual.
- Language toggles should lead directly to the same content in the other language. Link text to English or French content must direct the reader to that language version.
- Content in languages other than English or French should be posted as accessible Portable Document Format (PDF) files, not coded as HyperText Markup Language (HTML).
- Put a copyright statement in the footer of every non-HTML document published to the public web. Public websites should link to the central copyright statement at https://www.ontario.ca/page/copyright-information.

## Titles, Links, and Documents

- Apply metadata to every format of web resource as GO-ITS 400DTS Information Resource Description Metadata Standard requires.
- Give every page a descriptive, concise `<title>` element that is unique to that page. It should use the format `document title | website name` and stay within 65 characters. When the website name includes a ministry name, it must put "Ontario" before the ministry name.
- Links should be descriptive and should follow the accessibility rules, the ODS, the Ontario.ca style guide, and the Ontario.ca Web Content Editing Guide.
- Show the format and file size in every link to a non-HTML file, such as `Brochure [PDF — 2 MB]`. Make every link to an alternate language or format version lead to an equivalent page.
- Create redirects for important pages when a relaunch or content reorganization changes their links.
- Refer to websites by a fully qualified domain name, never by an Internet Protocol (IP) address or server name.
- Never use proprietary formats that require users to buy a plug-in or software, and never post Microsoft Office documents to public-facing websites unless legislation authorizes it. Office documents on intranet websites should not contain earlier versions or edits, such as tracked changes.
- Where information is available only as a PDF because of a legal or security requirement, make it as accessible as technically possible. Make secure documents accessible to assistive technologies.
- Save alternate-format files so that they work across platforms without degrading the document or compromising security requirements. They should be as small as possible.

## Multimedia and Navigation

- Make public-facing images, video, audio, and applications accessible and compliant with language requirements. Provide a way to navigate through or skip any audio or video presentation that is incidental to the user experience.
- Public-facing websites should use photographs and videos taken in Ontario of Ontario residents, such as from ImageON, the government's digital asset library, and should use third-party stock or generic settings only when no alternative exists.
- Embed public-facing videos from the Government of Ontario's central YouTube channels, which host all videos for public-facing websites. For images, maps, and videos on ontario.ca or its subsites, also follow the Ontario.ca Web Content Editing Guide.
- Let users browse all content, with breadcrumbs and navigation pages, and also let them search any content of more than 30 pages or records. Add a Related section that links to other relevant pages where needed.
- Websites should provide plain-language "file not found" (404) pages that offer resources and suggest corrections for common errors. When moving popular documents, they should use a proxy redirect or a "moved permanently" (301) page that explains how to reach the information before redirecting.

## Search and Analytics

- Make every website indexable by the ontario.ca Search Service. Serve it with a valid certificate from the OPS-approved enterprise service provider, make dynamically generated content, such as JavaScript-rendered pages, available as static, crawlable files, and meet the title and metadata rules in this file.
- Where a website with non-classified, low-sensitivity information requires search, use the ontario.ca Search Service.
- Websites should provide a valid `sitemap.xml` file and `robots.txt` file where applicable.
- On a search results page, show a search box with the current query at the top, provide refinement options or query assistance, such as filters, sorting, auto-completion, or suggestions, show the total number of results and the number per page, present accurate page titles with concise descriptions based on meta descriptions, and avoid duplicate results for the same address.
- Collect statistics about site performance and traffic on every website. Track only aggregate behaviour, never use the data to identify individuals unless the law authorizes it, use it only to understand and improve the site, and never share it with or use it in other third-party services or websites for other purposes.
- For ontario.ca websites, prefer the government's centralized analytics setup, arranged with Cabinet Office Communications.

## Privacy and Security

- Display a Notice of Collection clearly and conspicuously at or before every point where personal information is collected. State the legal authority for the collection, its purpose, and the contact information of the individual whom the public can contact with questions about the notice.
- Provide a link to the Ontario Government's central privacy statement at https://www.ontario.ca/page/privacy-statement.
- Collect only the personal information that the service needs, and mark every non-essential field as optional. Collect more only when a statute authorizes it or the person explicitly consents.
- Never use personal information in application or server access logs, such as IP addresses, to identify individuals unless legislation authorizes the program or service to do so. Personal data used for analytics should be anonymized or grouped so that individuals cannot be identified.
- Keep personal information no longer than the service or legislation requires, dispose of it securely under OPS policies, and follow the records retention schedules under the Archives and Recordkeeping Act, 2006, as appropriate.
- Design state management mechanisms, such as sessions, cookies, and tokens, to prevent unauthorized access to personal information.
- Serve every website over Hypertext Transfer Protocol Secure (HTTPS) with a valid certificate from the OPS-approved enterprise service provider, and protect every public-facing website with a web application firewall from that provider.
- Comply with GO-ITS 25.12 for cryptography, GO-ITS 25.13 for web application security, and GO-ITS 42 for vulnerability management, in addition to `secure-coding.instructions.md`.

## Forms, Feedback, Log-in, and Subscriptions

- Give every public-facing website a feedback mechanism, and list alternate channels where available, such as telephone, teletypewriter, fax, email, and postal address. Feedback forms must also comply with the Accessible Customer Service Policy and the Ontario Government Common Service Standards.
- Use anti-spam measures wherever an email address is published.
- On a log-in screen, identify and describe the service being logged in to, give registration instructions, and provide help and a way to recover forgotten or lost credentials. The description and instructions may be on the same page or linked.
- On a subscription sign-up page, provide a Notice of Collection and a plain-language description of the service. Use subscriber information only for the stated purpose, store it securely out of public reach, limit access to authorized personnel, and protect it as the Corporate Policy on Information Sensitivity Classification requires.
- Never use mechanisms that reveal the actions or preferences of individual subscribers, such as links with unique identifiers, unless legislation requires them and the service needs them to operate. Give every subscription email an unsubscribe option and a link to a feedback form.

## Approvals and Directives

These obligations need people or teams outside the code. When the work triggers one, tell the user instead of assuming that it was met.

- Cabinet Office Communications must approve new public-facing websites, ontario.ca keywords, which are vanity addresses such as `ontario.ca/<keyword>`, and new ministry social media channels. Ministries must consult it on all ontario.ca requests, on new platforms, products, or applications, and on integration with enterprise platforms.
- Never register a new external domain name; use only subdomains of ontario.ca or gov.on.ca. The OPS Domain Registrar approves domain requests and owns every public-facing domain, every domain name must follow its Domain Name Guidelines, and decommissioned domains must be reported to it and recorded in the OPS websites database.
- A public-facing website that collects, uses, or discloses personal information needs a completed Privacy Impact Assessment.
- For a public-facing website, engage the Cyber Security Division of the Ministry of Public and Business Service Delivery and Procurement to decide whether a Threat Risk Assessment or penetration test is required. The assessment should be revisited after significant changes to the system architecture or data flows. Report security incidents to that division as GO-ITS 25.20 specifies.
- Cabinet Office Communications and the Premier's Office must approve paid campaigns and, before production and distribution, public-facing video content. Websites used in marketing campaigns must follow government advertising directives and legislation. Public communications must use an ontario.ca keyword, and paid marketing must lead to an ontario.ca page, unless Cabinet Office Communications grants an exemption. Never use external or gov.on.ca domain names for advertising.
- Inform the Enterprise Web Coordinators and the Web Coordinators Committee co-chairs of new web initiatives through the ministry or cluster Web Coordinator, communicate government-wide changes through that committee, and keep the website's listing in the OPS websites database current.
- Ministries and provincial agencies must follow Ontario's Responsible Use of Artificial Intelligence Directive.
