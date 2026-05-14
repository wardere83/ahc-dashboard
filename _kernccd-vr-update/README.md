# kernccd VR Project Profile update (staged)

Staged here under `wardere83/ahc-dashboard` because the Claude Code
session lacks write access to `Bulle-Consulting/kernccd`.

## Files in `_kernccd-vr-update/`

- `index.html` - full patched dashboard (drop-in replacement for
  `Bulle-Consulting/kernccd:index.html`)
- `vr-card.patch` - two-commit unified diff against `70fa037`:
  1. Condense Project Profile hero card and add interactive VR avatar
  2. Strip em/en dashes from dashboard copy

## Apply to `Bulle-Consulting/kernccd`

```
git clone https://github.com/Bulle-Consulting/kernccd.git
cd kernccd
git checkout -B claude/update-project-profile-vr-G2cIG origin/main
curl -fsSL https://raw.githubusercontent.com/wardere83/ahc-dashboard/kernccd-vr-update-staging/_kernccd-vr-update/index.html > index.html
git commit -am "Project Profile: condense card, add VR avatar, strip long dashes"
git push -u origin claude/update-project-profile-vr-G2cIG
```
