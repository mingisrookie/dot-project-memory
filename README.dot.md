# dot integration guide

This repository supplies a portable skill, not an installer or an account-wide configuration change. Its human-facing overview is [README.md](README.md).

## Load the package

Use the host's supported skill import or installation mechanism for `skills/dot-project-continuity/`. Load `SKILL.md` when the current request depends on ongoing project context. Its linked reference is conditional, not required reading on every turn.

The optional `agents/openai.yaml` is presentation metadata for compatible Codex hosts. No tool dependency or new access grant is declared. Do not assume the host supports explicit `$skill-name` invocation, persistent storage, automatic discovery, or installation merely because it can read these files.

## Map to existing capabilities

- Read relevant conversation, task, or artifact context through the host's authorized interfaces
- Use existing project identifiers and storage conventions where they are available
- Persist changes only when the destination, access, and intended use are authorized
- When no persistent store is available, use conversation-local context and a concise carry-forward summary
- Keep host instruction precedence, permissions, and confirmation requirements intact

The skill requires no particular storage schema, fixed file set, scheduled process, external account, or API. Do not create those as an installation side effect. Project labels organize context; they do not create access controls.

## Verify an integration

Confirm that the host actually loaded the intended version. Exercise a small synthetic case from [evals/cases.json](evals/cases.json), withholding its grading criteria from the responding assistant. Observe both its answer and proposed actions. Report the host, loading method, observed behavior, and whether persistence was tested.

A packaging check, successful Git publication, or sensible one-turn response is not evidence of permanent installation, global availability, or cross-session recall. Describe only the capabilities verified in that host.

Keep real user data out of this repository and all public test reports. No installation, publication, or live integration is performed by these files themselves.
