# Feedback Service Capabilities

- **Runtime:** Cloudflare Workers, deployed with `wrangler.mixu.toml`.
- **Domain:** `feedback.michael-schindler.dev` as a Cloudflare Worker Custom Domain.
- **GitHub:** Private GitHub App `mixu-client-feedback`; repository access is granted per customer project.
- **Secrets:** Bitwarden Secrets Manager references only:
  - `integrations/github/mixu-client-feedback/auth-token-secret` (created)
  - `integrations/cloudflare/mixu-feedback-worker/token` (pending approval)
  - `integrations/github/mixu-client-feedback/app-id` (pending GitHub App registration)
  - `integrations/github/mixu-client-feedback/private-key` (pending GitHub App registration)
- **Client integration:** Enable the widget only in preview deployments. Each host app mints a short-lived BugDrop token after validating its Cloudflare Access session.
- **Storage:** Screenshots are written to the private target repository's dedicated `bugdrop-screenshots` branch. Exclude that branch from builds and deployments.
- **Node:** Use the repository's `.nvmrc` (Node 22) or a newer supported LTS release.

Never place Worker tokens, GitHub App keys, generated `.dev.vars`, or PEM files in Git.
