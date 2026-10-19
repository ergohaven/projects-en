# Ergohaven projects — EN production

Deployment wrapper for https://projects.eh.industries/phenom/.

**Shared source:** [ergohaven/projects](https://github.com/ergohaven/projects). Do not copy product source, templates or assets into this repository.

The manual **Deploy production landing** workflow calls the shared deployment workflow at an immutable reviewed revision. Supply the full approved source commit SHA as `source_ref`. Both production languages must be published from the same source SHA. See the source repository README for the complete deployment and DNS procedure.

Only Phenom is published; other product drafts stay in the GitHub preview. The domain root redirects to `/phenom/`.

```sh
gh workflow run deploy.yml --repo ergohaven/projects-en -f source_ref=15af5e1d2c382ceb5425abfd71c9d916e313cb88
```

This repository uses its own Pages deployment token and OIDC identity. No cross-repository deployment secret is needed. Update the pinned reusable-workflow SHA here only when intentionally adopting reviewed deployment-logic changes.
