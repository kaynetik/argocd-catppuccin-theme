# ArgoCD Catppuccin Theme

Custom theme for ArgoCD using the [Catppuccin](https://github.com/catppuccin/palette) palette. Dark mode uses **Frappe**, light mode uses **Latte**.

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

Hard-refresh the browser (`Cmd+Shift+R` / `Ctrl+Shift+R`).

### 4. Switch between themes

ArgoCD stores theme preference in browser `localStorage`. Toggle between dark and light at **Settings > Appearance** in the UI.

## Palette (Dark -- Frappe)

| Role               | Token        | Hex       |
|:--------------------|:-------------|:----------|
| Background          | Base         | `#303446` |
| Panels              | Mantle       | `#292c3c` |
| Deepest layer       | Crust        | `#232634` |
| Surface             | Surface 0-2  | `#414559` - `#626880` |
| Main text           | Text         | `#c6d0f5` |
| Subdued text        | Subtext 0-1  | `#a5adce` - `#b5bfe2` |
| Primary accent      | Blue         | `#8caaee` |
| Links               | Blue         | `#8caaee` |

## Palette (Light -- Latte)

| Role               | Token        | Hex       |
|:--------------------|:-------------|:----------|
| Background          | Base         | `#eff1f5` |
| Panels              | Mantle       | `#e6e9ef` |
| Deepest layer       | Crust        | `#dce0e8` |
| Surface             | Surface 0-2  | `#ccd0da` - `#acb0be` |
| Main text           | Text         | `#4c4f69` |
| Primary accent      | Blue         | `#1e66f5` |

## Coverage

- Sidebar navigation and filter panel
- Top bar / breadcrumbs / action buttons
- Application tiles and table list
- Application status panel
- Resource tree nodes and labels
- Sliding panels and white-box containers
- Tabs, buttons, form inputs
- Dropdown menus (rendered outside the theme wrapper)
- Autocomplete lists (Labels, Projects, Clusters, Namespaces)
- Select dropdowns with search
- Popup modals
- Login page and logout button
- Search bar
- Scrollbars (Webkit)
- Banner bar

## Customization

All Catppuccin colors are declared as CSS custom properties (`--ctp-*`) under `.theme-dark` and `.theme-light` selectors. To swap to a different Catppuccin flavor (Macchiato, Mocha), replace the hex values from the [Catppuccin palette](https://github.com/catppuccin/palette).

> [!NOTE]
> Elements like `.argo-dropdown__content` and `.autocomplete__items` are rendered as direct children of `<body>`, outside the `.theme-dark` / `.theme-light` wrapper div. These are styled with hardcoded Frappe hex values at the bottom of the CSS file since CSS variables from the wrapper are not inherited.

## References

- [ArgoCD Custom Styles documentation](https://argo-cd.readthedocs.io/en/stable/operator-manual/custom-styles/)
- [Catppuccin palette](https://github.com/catppuccin/palette)
