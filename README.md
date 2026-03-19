# codex

Nix packaging for `@openai/codex` using Bun and `bun2nix`.

## Package

- Upstream package: `@openai/codex`
- Pinned version: `0.115.0`
- Installed binary: `codex`
- Upstream executable invoked by Bun: `codex`

## What This Repo Does

- Uses `bun.lock` and generated `bun.nix` as the dependency lock surface for Nix
- Builds the upstream package as an internal Bun application with `bun2nix`
- Exposes only the canonical binary name `codex`
- Provides a manifest sync script for updating the pinned npm metadata

## Files

- `flake.nix`: flake entrypoint
- `nix/package.nix`: Nix derivation
- `nix/package-manifest.json`: pinned package metadata and exposed binary name
- `scripts/sync-from-npm.ts`: updates pinned npm metadata without changing the canonical output binary

## Notes

- The default `out` output installs the longform binary name `codex`.
- The shortform wrapper `cod --dangerously-bypass-approvals-and-sandbox` is available as a separate Nix output, not in the default `out` output.
