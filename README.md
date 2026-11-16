# Documentation Theme (Zensical)

Stylesheets, fonts and images for Dyalog documentation built with
[Zensical](https://zensical.org/), the successor to Material for MkDocs. This is
the `zensical` branch of
[`documentation-theme`](https://github.com/Dyalog/documentation-theme); `main`
targets Material for MkDocs.

## What's here

| Path                  | Contents                                                  |
| --------------------- | --------------------------------------------------------- |
| `css/dyalog.css`      | The theme: fonts and light/dark colour schemes             |
| `fonts/APL387`        | [APL387](https://github.com/Dyalog/APL387), for all code |
| `fonts/IBMPlexSans`   | Body text, regular and bold with italics                   |
| `images`              | Favicon, Dyalog logos and issue-type icons                 |

## Usage

Zensical only copies files from inside `docs_dir` and does not follow symlinks,
so add the theme under `docs/`:

```shell
git submodule add -b zensical https://github.com/Dyalog/documentation-theme docs/documentation-theme
```shell

Then in `zensical.toml`:

```toml
[project]
extra_css = ["documentation-theme/css/dyalog.css"]

[project.theme]
variant = "classic"
logo = "documentation-theme/images/dyalog-logo_orange.svg"
favicon = "documentation-theme/images/dyalog-ide-cube-2025.2.svg"
font = false          # fonts are self-hosted, skip Google Fonts
features = ["content.code.copy", "navigation.sections"]

[[project.theme.palette]]
media = "(prefers-color-scheme: light)"
scheme = "default"
primary = "custom"    # colours come from dyalog.css
accent = "custom"
toggle.icon = "lucide/sun"
toggle.name = "Switch to dark mode"

[[project.theme.palette]]
media = "(prefers-color-scheme: dark)"
scheme = "slate"
primary = "custom"
accent = "custom"
toggle.icon = "lucide/moon"
toggle.name = "Switch to light mode"
```

## Licences

Each font directory has its own `LICENCE`. The root `LICENCE` covers the rest.
