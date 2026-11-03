---
description: Use when writing, changing, or reviewing code, scripts, configuration, containers, or infrastructure definitions. Covers the security workflow, self-review, severity handling, technology-specific rules, and defensive coding.
applyTo: "**/*.{ts,tsx,mts,cts,js,jsx,mjs,cjs,java,kt,kts,groovy,gradle,cs,py,go,rs,php,rb,swift,c,cc,cpp,h,hpp,html,sql,json,jsonc,xml,yml,yaml,toml,properties,tf,tfvars,bicep,ps1,psm1,sh,bash,zsh,bat,cmd},**/Dockerfile*,**/.env*"
---

# Secure Coding

Treat security as the primary design constraint, not a later refinement. Every generated or modified unit of code must be secure by default and must not introduce a known or probable vulnerability.

## Workflow

1. **Threat-aware design.** Before writing code, identify the data it handles, the trust boundaries it crosses, and what an attacker could exploit.
2. **Secure implementation.** Write code that is secure by construction. Apply the Open Worldwide Application Security Project (OWASP) Top 10, the SANS Top 25, and any applicable Common Weakness Enumeration (CWE) mitigations for the language and framework in use.
3. **Self-review.** After generating code, review it for vulnerabilities before presenting it as a recommendation.
4. **Remediate before recommending.** Handle every finding as Severity Handling requires. Never present insecure code as a final recommendation, even with a disclaimer.
5. **Document the rationale.** When a non-obvious security decision is made, add a brief inline comment prefixed with `// @security:` that explains why.

## Self-Review Coverage

The self-review must check, at minimum, for:

- Injection flaws, including Structured Query Language (SQL), operating-system command, Lightweight Directory Access Protocol (LDAP), XPath, template, and header injection
- Broken authentication and broken session management
- Sensitive data exposure, including secrets, personally identifiable information (PII), and tokens in logs, responses, or source
- Extensible Markup Language (XML) and JavaScript Object Notation (JSON) external-entity attacks and insecure deserialization
- Broken access control, including missing authorization checks, insecure direct object references, and privilege escalation
- Security misconfiguration, including overly permissive Cross-Origin Resource Sharing (CORS), verbose error messages, and enabled debug flags
- Cross-site scripting (XSS), whether reflected, stored, or based on the Document Object Model (DOM)
- Path traversal
- Cross-site request forgery (CSRF), where applicable
- Known-vulnerable dependencies and deprecated cryptographic algorithms
- Race conditions, time-of-check-to-time-of-use defects, and insecure temporary-file handling

## Severity Handling

- **Critical or high:** Fix in the generated code before presenting it. No exceptions.
- **Medium:** Fix, or when a fix is structurally impractical in the current change, flag it with a `// @security-todo:` comment that explains the residual risk.
- **Low or informational:** Fix where practical; otherwise note it in a comment for future hardening.

## Technology-Specific Rules

- **Server-side application code:** Never reflect unsanitized user input in an error message. Set the `HttpOnly` and `Secure` cookie flags.
- **Browser application code:** Rely on the framework's built-in output sanitization, and never bypass it without peer review. Avoid raw markup bindings that carry user-controlled data. Validate route and query parameters. Do not store credentials or long-lived tokens in browser storage.
- **Databases:** Never return a raw database error to a client.
- **Containers and infrastructure as code:** Never embed secrets in images, manifests, or templates. Run containers as a non-root user. Pin base-image versions. Limit container capabilities.
- **Shell and automation scripts:** Quote every variable expansion. Use `--` to terminate option parsing. Never pass dynamic input to `eval`.

## Defensive Coding

These rules apply to all code, including application code, tests, scripts, and infrastructure as code. They are machine-checkable so that reviewers and automated tools can enforce them.

- Never trust client-supplied or environment-supplied data. Validate every input at each external boundary, such as request parameters, path segments, headers, and body fields: check type, format, length, range, and permitted characters, then canonicalize and sanitize it before use. Validate client-supplied data on the server before applying business logic.
- Guard explicitly against null, undefined, and empty values before dereferencing.
- Choose fail-safe defaults. On error or missing data, deny the action, take no action, or expose the minimum.
- Never swallow exceptions. Catch at the appropriate layer, add context, log at error or warning level, and rethrow or map to a domain error.
- Release resources deterministically using constructs such as try-with-resources or `finally`. Close connections, files, streams, and subscriptions.
- Use parameterized queries and prepared statements. Never build a query or a command line by string concatenation, and never pass unsanitized input to a process-execution interface.
- Apply the correct encoding or escaping for each output context, including markup, JSON, SQL, and shell.
- Never log secrets or PII. Redact sensitive fields consistently and use structured logs with correlation identifiers.
- Apply timeouts and bounded retries to remote calls, with exponential backoff and circuit breakers where appropriate.
- Apply least privilege to every resource: file access, database accounts, network access, and service accounts.
- Add unit tests for normal, edge, and failure cases, including invalid input. Add integration or contract tests when a public interface changes.
- Run static analysis, linters, and security scanners in continuous integration, and block merges on critical security or reliability violations.
- Mark unusual defensive checks with a machine-readable comment such as `// @defensive: reason` so that automated reviewers can find the intent.

Treat the following as failing conditions that must be fixed before merging: missing input validation, unchecked null dereferences, swallowed exceptions, string-built queries or commands, unreleased resources, secrets in source or logs, and missing negative tests.
