# ArgoCD Catppuccin Frappe Theme

Custom dark theme for ArgoCD using the [Catppuccin Frappe](https://github.com/catppuccin/palette) palette.

## Prerequisites

1. ArgoCD running with dark mode enabled (user preference)
2. A public repository or CDN to host the CSS file

## Setup

### 1. Host the CSS

Push `catppuccin-frappe.css` to a public GitHub repository (e.g. `kaynetik/argocd-catppuccin-theme`).

The file is then available via jsDelivr CDN:

```
https://cdn.jsdelivr.net/gh/kaynetik/argocd-catppuccin-theme@main/catppuccin-frappe.css
```

### 2. Configure ArgoCD

Add `ui.cssurl` to the `argocd-cm` ConfigMap (or via Helm values under `configs.cm`):

```yaml
configs:
  cm:
    ui.cssurl: "https://cdn.jsdelivr.net/gh/kaynetik/argocd-catppuccin-theme@main/catppuccin-frappe.css"
```

### 3. Refresh the UI

Hard-refresh the browser (`Cmd+Shift+R` / `Ctrl+Shift+R`). The theme loads on every page visit.

## Palette

| Role | Color | Hex |
|------|-------|-----|
| Background (base) | Base | `#303446` |
| Panels (mantle) | Mantle | `#292c3c` |
| Deepest (crust) | Crust | `#232634` |
| Surface | Surface 0/1/2 | `#414559` / `#51576d` / `#626880` |
| Main text | Text | `#c6d0f5` |
| Subdued text | Subtext 0/1 | `#a5adce` / `#b5bfe2` |
| Primary accent | Blue | `#8caaee` |
| Secondary accent | Lavender | `#babbf1` |
| Success / Healthy | Green | `#a6d189` |
| Warning / OutOfSync | Yellow | `#e5c890` |
| Error / Degraded | Red | `#e78284` |
| Info / links | Mauve | `#ca9ee6` |

## Coverage

The theme targets all major ArgoCD UI components:

- Top bar and breadcrumbs
- Sidebar navigation
- Application list (table and tile views)
- Application detail panels
- Resource tree (node graph, pods, labels)
- Sliding panels and white-box containers
- Tabs, buttons, dropdowns
- Form inputs and focus states
- Diff viewer (added/removed line highlights)
- Tooltips and popovers
- Scrollbars
- Health and sync status icon colors
- Login page
- Banner bar
- Mobile responsive adjustments

## Customization

All Catppuccin colors are declared as CSS custom properties (`--ctp-*`) at the top of the file.
To switch to a different Catppuccin flavor (Latte, Macchiato, Mocha), replace the hex values
with the corresponding palette from https://github.com/catppuccin/palette.

## References

- [ArgoCD Custom Styles docs](https://argo-cd.readthedocs.io/en/stable/operator-manual/custom-styles/)
- [Catppuccin palette](https://github.com/catppuccin/palette)

