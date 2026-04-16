## YPoint V2 Icons (dev bundle)

Trong `ypointv2/` hiện các “icon” đang được render bằng font:
- `Material Icons Round` (dùng cho các thẻ `<span class="material-icons-round">...</span>`)
- `Material Symbols Outlined` (dùng cho các thẻ `<span class="material-symbols-outlined">...</span>`)

File này chỉ để dev copy/paste các thẻ import vào `<head>` khi dùng các trang `ypointv2/*`.



## Local font bundle (offline dev)
- `material-icons-round-local.css`
- `material-symbols-outlined-local.css`
- Font binaries under `icons/material-icons-round/` (OTF) and `icons/material-symbols-outlined/` (TTF)

To use in a mobile/web view without network:
- Reference `material-icons-round-local.css` and `material-symbols-outlined-local.css` from your HTML/React/Vue entry.
- Those CSS files reference the local font binaries by relative paths.

Dev helper:
- `used-icons-material-icons-round.txt`
- `used-icons-material-symbols-outlined.txt`

## Vector icons (SVG)
- `ypointv2/icons/svg/stars-circle-amber.svg`
- `ypointv2/icons/svg/stars-circle-amber-dark.svg`
- `ypointv2/icons/svg/stars-only.svg`
- `ypointv2/icons/svg/workspace_premium.svg`
- `ypointv2/icons/svg/workspace_premium-white.svg`
- `ypointv2/icons/svg/workspace_premium-silver.svg`
- `ypointv2/icons/svg/workspace_premium-bronze.svg`
- `ypointv2/icons/svg/workspace_premium-glow-yellow20.svg`

