# kernccd VR Project Profile update (staged)

This branch stages the change requested for `Bulle-Consulting/kernccd`'s
dashboard. The Claude Code session couldn't push directly to that repo —
the GitHub App is installed there read-only and `wardere83` isn't a
collaborator with write access — so the artifacts live here under
`wardere83/ahc-dashboard` instead.

## Files in `_kernccd-vr-update/`

- `index.html` — full patched dashboard (drop-in replacement for
  `Bulle-Consulting/kernccd:index.html`)
- `vr-card.patch` — unified diff against the previous `index.html`
  (commit `988c2d5`)

## What the change does

Condenses the Project Profile hero card and adds an interactive
SVG avatar wearing a VR headset:

- Removes `Kern Community College District · 2100 Chester Avenue, Bakersfield, CA 93301`
- Removes `Tier 1 Award` label
- Removes `2026-2028 EEO IBP Grant · Tier 1` eyebrow
- Shrinks the program title (24px -> 17px) and `$150,000` figure (32px -> 18px)
- Inserts an animated SVG avatar that pans left/right and tilts up/down
  on a 7s loop; tracks the cursor on hover; respects
  `prefers-reduced-motion` and the in-app a11y motion toggle

## Apply to `Bulle-Consulting/kernccd`

```
git clone https://github.com/Bulle-Consulting/kernccd.git
cd kernccd
git checkout -B claude/update-project-profile-vr-G2cIG origin/main
curl -fsSL https://raw.githubusercontent.com/wardere83/ahc-dashboard/kernccd-vr-update-staging/_kernccd-vr-update/vr-card.patch | git am
git push -u origin claude/update-project-profile-vr-G2cIG
```

Or just overwrite `index.html` with the staged copy:

```
curl -fsSL https://raw.githubusercontent.com/wardere83/ahc-dashboard/kernccd-vr-update-staging/_kernccd-vr-update/index.html > index.html
git commit -am "Condense Project Profile hero card and add interactive VR avatar"
git push
```
