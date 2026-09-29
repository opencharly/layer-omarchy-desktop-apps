# omarchy-desktop-apps

The desktop applications Omarchy ships, as a charly layer — the file manager,
document and image viewers, productivity apps and input methods the
distribution's application menu and default MIME associations point at.

The `omarchy-desktop-apps` candy installs the graphical applications Omarchy's
own base package list names. Without them the desktop still starts, but every
file-open action resolves to nothing. The set includes Nautilus with its gvfs
backends, LibreOffice, Obsidian, Evince, imv, Xournal++, the Omarchy-published
`omawrite`/`omacalc`, LocalSend, and the fcitx5 input-method stack (GTK + Qt
bridges).

## What it provides

| Property | Value |
|---|---|
| Layer / candy | `omarchy-desktop-apps` |
| Requires | `layer-omarchy-base` (the foundation layer) |
| Installs | Nautilus + gvfs backends, LibreOffice, Obsidian, Evince, imv, Xournal++, omawrite, omacalc, LocalSend, fcitx5 + gtk/qt bridges |
| Service / port | none |

## How to use it

Compose the layer by pinning the member candy's sub-path in a desktop box's
`candy:` list:

```yaml
my-omarchy-desktop:
  candy:
    base: omarchy
    candy:
      - '@github.com/opencharly/layer-omarchy-base/candy/omarchy-base:v2026.242.0701'
      - '@github.com/opencharly/layer-omarchy-desktop-apps/candy/omarchy-desktop-apps:v2026.242.0635'
```

## Layout

- `charly.yml` — repo shape: the `discover:` rule that finds the member candy.
- `candy/omarchy-desktop-apps/charly.yml` — the candy entity (the `distro:`
  package arm and the `plan:` `check:` assertions).
- `.github/workflows/tag-on-merge.yml` — CalVer tag + `CHANGELOG/` on merge.
- `README.md` — this user overview.

## Related

- Foundation: `/charly-distros:omarchy-base`.
- Sibling layers: `/charly-distros:omarchy` and the other
  `opencharly/layer-omarchy-*` repos.
- [`opencharly/opencharly`](https://github.com/opencharly/opencharly) — the umbrella.
