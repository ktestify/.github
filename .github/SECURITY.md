# Security Policy

## Supported Versions

KTestify is pre-1.0, and each repository is versioned on its own. We release security fixes for the **latest released version** of each module only, so please upgrade before reporting.

| Version            | Supported |
|--------------------|-----------|
| Latest release     | ✅ Yes    |
| Older releases     | ❌ No     |

## Reporting a Vulnerability

**Please do NOT open a public GitHub issue, pull request or discussion for security vulnerabilities.**

Use one of the following private channels instead.

### Option 1: GitHub private vulnerability reporting (preferred)

1. Open the repository the vulnerability is in, for example
   [ktestify-core](https://github.com/ktestify/ktestify-core) or
   [ktestify-cucumber](https://github.com/ktestify/ktestify-cucumber).
2. Go to the **Security** tab and click **Report a vulnerability**.

Not sure which repository is affected? Report it on
[ktestify-core](https://github.com/ktestify/ktestify-core/security/advisories/new) and we'll move it.

### Option 2: Email

Send a report to [security@ktestify.xyz](mailto:security@ktestify.xyz). Please include:

- The affected repository and version(s)
- A description of the vulnerability and its potential impact
- Steps to reproduce, ideally a minimal scenario or test
- A suggested fix, if you have one

## What to Expect

1. **Acknowledgement** within **3 business days**.
2. **Triage**: we confirm the issue and assess its severity using CVSS.
3. **Fix**: developed privately. We aim to release a fix within **14 days** for critical issues.
4. **Coordinated disclosure**: we agree on a disclosure date with you and let you know before the release goes out.
5. **CVE**: we request a CVE ID for confirmed vulnerabilities of significant severity, through GitHub Security Advisories.
6. **Credit**: reporters are credited in the advisory and release notes, unless they prefer to stay anonymous.

## Scope

This policy covers every repository in the [ktestify](https://github.com/ktestify) organization, including:

- `ktestify-core` and `ktestify-cucumber`
- First-party plugins (`ktestify-plugin-*`) and the plugin archetype
- `ktestify-parent`
- The documentation site (`ktestify-doc`, docs.ktestify.xyz)

Examples of what we especially want to hear about:

- Secrets (credentials, tokens, webhook URLs, connection strings) leaking into logs, reports or notifications
- Unsafe handling of payload files, dynamic variables, XML/XPath or scripts that could lead to code execution, XXE or path traversal
- Insecure defaults in configuration

**Out of scope**

- Vulnerabilities in third-party dependencies with no impact on KTestify. Please report those upstream. If a dependency vulnerability *is* exploitable through KTestify, we do want to know.
- Issues that require an attacker to already control your test code, configuration or CI environment.
- Third-party plugins not maintained in the ktestify organization.