---
description: Apply secure-by-default practices when writing, changing, or reviewing code, scripts, configuration, containers, and infrastructure definitions.
applyTo: "**/*.{ts,tsx,mts,cts,js,jsx,mjs,cjs,java,kt,kts,groovy,gradle,cs,py,go,rs,php,rb,swift,c,cc,cpp,h,hpp,html,sql,json,jsonc,xml,yml,yaml,toml,properties,tf,tfvars,bicep,ps1,psm1,sh,bash,zsh,bat,cmd},**/Dockerfile*,**/.env*"
---

# Secure Coding

Treat security as a design constraint. Do not introduce a known or probable vulnerability in generated or modified work. Follow applicable project security requirements and established framework protections.

## Workflow

1. Identify sensitive data, trust boundaries, entry points, and plausible threats relevant to the change.
2. Apply relevant secure-design guidance, such as OWASP, CWE, and vendor-specific guidance, without treating broad checklists as a substitute for context.
3. Review changed code and configuration for security defects before presenting the result.
4. Remediate vulnerabilities introduced by the change or directly within the approved scope before recommending the change.
5. Report pre-existing findings outside the approved scope separately. Do not silently expand the task into unrelated remediation; request approval where scope must change.
6. Add a code comment only when a security decision would otherwise be unclear. Use the comment syntax and conventions of the language; do not add a comment to every defensive check.

## Review coverage

Consider, where relevant:

- Injection, including SQL, command, LDAP, XPath, template, and header injection.
- Authentication, session handling, and authorisation, including insecure direct object references and privilege escalation.
- Input validation, output encoding, cross-site scripting, path traversal, and cross-site request forgery.
- Secrets, personal information, tokens, sensitive logs, and error disclosure.
- Deserialisation, XML external entities, and unsafe file handling.
- Security configuration, CORS, dependency vulnerabilities, and deprecated cryptography.
- Race conditions, resource exhaustion, timeouts, retries, and denial-of-service exposure.

## Defensive defaults

- Treat client-supplied and external data as untrusted. Validate type, format, length, range, and permitted values at trust boundaries.
- Use parameterised queries and safe process APIs. Do not build SQL statements or shell commands by concatenating untrusted input.
- Preserve framework output sanitisation. Encode output for its destination context.
- Enforce authorisation on the server and apply least privilege to identities, data, files, networks, and service accounts.
- Use fail-safe defaults. Do not reveal secrets, personal information, stack traces, or raw internal errors to unauthorised users.
- Store secrets in approved secret-management facilities, not source, images, manifests, or logs.
- Handle exceptions deliberately. Preserve diagnostic context without swallowing failures or exposing sensitive details.
- Release resources deterministically. Use bounded timeouts and retries for remote operations where appropriate.
- For containers, use least privilege, avoid embedded secrets, and use approved/pinned base images.
- For shell scripts, quote expansions, handle option parsing safely, and never pass dynamic input to `eval`.
- Add appropriate negative tests for changed security-sensitive behaviour.

## Findings and severity

Prioritise findings by credible impact, likelihood, and confidence. Fix critical or high-severity defects introduced by the work. For existing out-of-scope defects, provide evidence and recommend remediation rather than changing unrelated code without approval. Record residual risk and verification not performed.
