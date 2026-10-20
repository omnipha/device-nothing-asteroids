# AGENTS.md

- English only. Compact. No secrets, tokens, person names, or host addresses.
- Scope: issues and tests for `device-nothing-asteroids` only.
- Shared kernel work follows `omnipha/linux-sm7635` AGENTS.md; some linux-* repos track sources without carrying patches. Package changes belong in `ports`. Build definitions belong in `images`.
- Never commit firmware blobs, credentials, or a full kernel tree.
- Link every cross-repo issue and pull request. A ports status update is a separate linked PR after public hardware evidence exists; never infer release availability from packages or image.yaml.
- For an unreleased device do not give flash commands; require a tested device-specific rollback procedure and physical authorization for writes.
- Device supervisor registration is separate. Nothing in this repo adds it to the main-host allowlist or auto-claims its issues.
