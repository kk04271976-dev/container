# kk04271976-dev/container

Free GUI container server using GitHub Actions + Chrome Remote Desktop.

## Setup

### 1. Git configuration (local)

```bash
cd kk04271976-dev
git config user.name "kk04271976-dev"
git config user.email "kk04271976-dev@users.noreply.github.com"
git remote add origin https://github.com/kk04271976-dev/container.git
```

For authenticated pushes, use the token in the URL:
```bash
git remote set-url origin https://kk04271976-dev:YOUR_TOKEN@github.com/kk04271976-dev/container.git
```

> ⚠️ **Security:** If you shared your GitHub token, revoke it at [github.com/settings/tokens](https://github.com/settings/tokens) and create a new one.

### 2. GitHub Secret (required)

Add **one** secret in **Settings → Secrets and variables → Actions**:

| Secret | Value |
|--------|-------|
| `CRD_AUTH_CODE` | Fresh auth code from [remotedesktop.google.com/headless](https://remotedesktop.google.com/headless) |

**Get a fresh code:** Visit https://remotedesktop.google.com/headless → Begin → Next → Authorize → copy the `--code="..."` value. **Codes expire in ~5 minutes and are single-use** — get a new one each time before running. PIN is hardcoded as `321654`.

### 3. Run the workflow

1. Get a **fresh** auth code from https://remotedesktop.google.com/headless (Begin → Authorize)
2. Update **CRD_AUTH_CODE** secret with the new code (Settings → Secrets)
3. Go to **Actions** → **Chrome Remote Desktop GUI Server** → **Run workflow**
4. When the job starts, connect at https://remotedesktop.google.com/access
5. Enter PIN: `321654`

## Notes

- **Ephemeral:** GitHub-hosted runners are destroyed when the job ends. Sessions last up to 6 hours.
- **Free tier:** 2,000 minutes/month for private repos on GitHub Free.
- **Fresh auth:** Generate a new `CRD_AUTH_CODE` each time you run the workflow.
