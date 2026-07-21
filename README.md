# northern-block

Github pages

## ⚠️ DEPRECATED — no new artifacts are written here

This repo is **frozen for new writes** as of 2026-07-21. All new schema, JSON-LD context, W3C schema, VCT, and revocation status list artifacts from eAPI's `credential` service are now published to **[`vc-artifact-registry`](https://github.com/Northern-Block/vc-artifact-registry)** instead.

**This repo must stay online permanently and nothing in it may be deleted, moved, or renamed.** Every file already published here has its GitHub Pages URL (`https://northern-block.github.io/northern-block/...`) permanently embedded inside credentials already issued to holders' wallets — in `credentialSchema`, `@context`, VCT `id`/`schema`/`jsonLdContext`, and `bitStringStatusListURL` fields. A wallet cannot be updated after issuance, so any credential ever issued against a URL in this repo depends on that exact file staying reachable at that exact path forever. Deleting this repo, or editing/moving any file in it, breaks every one of those credentials with no way to fix it after the fact.

### Why the move

- `vc-artifact-registry` adds an environment-prefixed path (`{dev|qa|prod|sandbox|stg|cs-prd}/...`) so artifacts from different deployment environments are no longer interleaved under ad-hoc ecosystem names, and one environment can't overwrite or be confused with another.
- It's served from a custom domain (`GITHUB_PAGES_DOMAIN`, domain root — not `{owner}.github.io/{repo}`) rather than this repo's default GitHub Pages URL.
- See `vc-artifact-registry`'s `README.md` for the current path/folder structure and the `docs/GITHUB-PATH-ENVIRONMENT-PLAN.md` / `docs/phases/phase-GPE-2.md` in `orbit-enterpriseapi-client` for why this repo could not simply be reorganized in place instead of replaced.

### What actually changed operationally

- `credential` and `issuer` apps' `GITHUB_OWNER`/`GITHUB_REPO`/`GITHUB_PAGES_DOMAIN` config now point at `vc-artifact-registry`, not `northern-block`.
- No content was migrated out of this repo — LOBs that published here before the cutover keep resolving their existing artifacts from here; only artifacts published after the cutover land in `vc-artifact-registry`. A given LOB's older and newer credentials may permanently resolve from two different repos, and that split is expected.

### If you're looking for something

- Looking for a **new** schema/context/VCT/status file → it's in `vc-artifact-registry`, not here.
- Looking for something issued **before the cutover** → it's still here, and will stay here indefinitely.
