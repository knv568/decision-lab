# Security Policy

Decision Lab is a **local Cursor workspace** for structured decision-making. It ships markdown, agent rules, and skills — not a deployed service, runtime, or network endpoint.

This policy covers security and privacy risks in the repository itself and how users should handle sensitive decision data on their machines.

## Supported versions

Only the latest commit on the default branch (`main`) receives security fixes. There are no versioned releases.

| Version | Supported |
| ------- | --------- |
| `main`  | Yes       |
| Older commits / forks | No |

## Reporting a vulnerability

If you find a security issue **in this repository** (for example, prompt-injection patterns in skills, instructions that could cause harmful agent behavior, or accidental exposure of real personal data in committed files), please report it privately:

1. Open a **[GitHub Security Advisory](https://github.com/knv568/decision-lab/security/advisories/new)** for this repo, **or**
2. Use [GitHub private vulnerability reporting](https://github.com/knv568/decision-lab/security/policy) if enabled, **or**
3. Contact the maintainer through their public GitHub profile: [@knv568](https://github.com/knv568).

Please include:

- A clear description of the issue and where it appears (file path, if applicable)
- Steps to reproduce or a proof of concept
- Impact assessment (who is affected and how)
- Suggested fix, if you have one

**Do not** open a public issue for undisclosed security problems.

We aim to acknowledge reports within **5 business days** and will coordinate disclosure once a fix is available.

## In scope

- Malicious or unsafe content in committed files (`.cursor/`, `templates/`, `reference/`, examples)
- Instructions that could reliably cause the agent to exfiltrate data, run destructive commands, or bypass stated privacy boundaries
- Accidental commit of real user data, credentials, or other secrets to the public repo
- Misleading documentation that could cause users to expose private session data

## Out of scope

- **Cursor IDE**, its extensions, or **AI model providers** — report those to their respective vendors
- General quality of AI advice during a decision session (this is facilitation, not professional counseling, legal, medical, or financial advice)
- Risks from a user choosing to share session files, chat logs, or synthesis output outside their machine
- Forks or copies of this repo not maintained here
- Social engineering against individual users

## Privacy and sensitive data

Decision sessions can contain **highly personal information** — career details, finances, relationships, health-adjacent context, and other private material.

### For users

- Session files live under `sessions/` and are **gitignored by default**. Keep real decisions local unless you explicitly choose to share them.
- `config.local.yaml` is gitignored; do not commit local overrides.
- Before pushing or opening a PR from a fork, verify you are not committing:
  - `sessions/*.md` (except sanitized files under `sessions/examples/`)
  - `.specstory/` or other local chat-history exports
  - API keys, tokens, or credentials in any file
- Treat **private synthesis** output as confidential. Sharing it sends that content to whatever service or person receives it (including cloud AI providers used by your editor).

### For contributors

- Never commit real decision sessions or identifying details.
- Example sessions must be clearly fictional or sanitized (see `sessions/examples/`).
- Do not add instructions that encourage committing user data or disabling `.gitignore` protections without an explicit, documented reason.

## Security best practices

- Clone or pull only from trusted sources ([`knv568/decision-lab`](https://github.com/knv568/decision-lab) or your own verified fork).
- Review changes to `.cursor/skills/` and `.cursor/rules/` before updating — these files guide agent behavior on your machine.
- If you maintain a public fork, keep the same `sessions/` and `config.local.yaml` ignore rules unless you document a deliberate change.

## Recognition

We appreciate responsible disclosure. With your permission, we may credit reporters in advisory notes or release notes. We do not currently offer a bug bounty program.
