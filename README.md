# Aniwhere CI

This is the **public CI/CD repository** for [Aniwhere](https://github.com/ali-pxr/aniwhere).

## How it works

1. Workflows checkout source code from the **private repository**
2. Source code is **encrypted with git-crypt** — no readable code in any repo
3. CI decrypts using a secret key, builds, and uploads artifacts
4. **Forks cannot access secrets** — code stays protected

## Build Artifacts

| Platform | Trigger | Artifact |
|----------|---------|----------|
| Linux | push / manual | `aniwhere-linux-x64.tar.gz` |
| Android | push / manual | APK + AAB |
| Windows | push / manual | `aniwhere-windows-x64.zip` |
| macOS | push / manual | `aniwhere-macos.zip` |
| iOS | push / manual | `aniwhere-ios.ipa` |
| **All** | manual only | All platforms |

## Manual Build

Go to **Actions** → select a workflow → **Run workflow**

## Security

- Source code is encrypted with [git-crypt](https://github.com/AGWA/git-crypt)
- `PAT` and `GIT_CRYPT_KEY` are stored as GitHub Secrets
- Secrets are **not available** to fork PRs
