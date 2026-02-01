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

### 2. GitHub Secrets (required)

Add these in **Settings → Secrets and variables → Actions**:

| Secret | Value |
|--------|-------|
| `CRD_AUTH_CODE` | Your one-time auth code from [remotedesktop.google.com/headless](https://remotedesktop.google.com/headless) |
| `CRD_PIN` | `321654` (6-digit PIN for remote desktop access) |

**Get a fresh auth code:** Visit https://remotedesktop.google.com/headless, click Begin → Next → Authorize, then copy the `--code="..."` value. Codes expire in minutes and are single-use.

### 3. Run the workflow

1. Go to **Actions** tab → **Chrome Remote Desktop GUI Server**
2. Click **Run workflow**
3. When the job starts, connect at https://remotedesktop.google.com/access
4. Enter PIN: `321654`

## Notes

- **Ephemeral:** GitHub-hosted runners are destroyed when the job ends. Sessions last up to 6 hours.
- **Free tier:** 2,000 minutes/month for private repos on GitHub Free.
- **Fresh auth:** Generate a new `CRD_AUTH_CODE` each time you run the workflow.
