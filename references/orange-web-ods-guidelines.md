# Orange Web And OUDS Guidance

Use this reference when applying Orange web-derived rules to WinUI or PySide6 interfaces.

## Source Hierarchy

Prefer sources in this order:

1. Target repo design-system files, if present.
2. Orange Design System web pages supplied by the user.
3. OUDS Web documentation.
4. Boosted documentation and the Orange Boosted Bootstrap repository.
5. ODS Charts documentation and repository for data visualisation.
6. OUDS iOS only as a sparse, secondary cross-check for platform-neutral naming or token concepts.

Do not use iOS, tvOS, watchOS, Android, or Flutter interaction guidance when a web/OUDS Web/Boosted source exists.

Primary source URLs:

- `https://system.design.orange.com/0c1af118d/p/76371f-master-and-small-logo`
- `https://system.design.orange.com/0c1af118d/p/76371f-master-and-small-logo/b/24906c`
- `https://system.design.orange.com/0c1af118d/p/43fadd-responsive-grids/b/42064a`
- `https://web.unified-design-system.orange.com/docs/0.5/layout/grid/`
- `https://boosted.orange.com/docs/5.3/`
- `https://github.com/Orange-OpenSource/Orange-Boosted-Bootstrap`
- `https://charts.unified-design-system.orange.com/`
- `https://github.com/Orange-OpenSource/ods-charts`
- `https://github.com/Orange-OpenSource/ouds-ios`

## Master And Small Logo

- Always use official Orange logo artwork. Do not redraw, recolor, distort, crop, or animate the Master logo.
- Treat the Master logo as the default logo when there is enough room.
- Use the Small logo when the Master logo would be below the digital minimum size.
- Use at least 50px for tablet/desktop Master logo rendering and at least 30px for mobile-scale rendering.
- Preserve clear space around the Master logo. Aim for `0.5X`; use `0.25X` only where space is constrained.
- Preserve `0.25X` clear space around the Small logo.
- Keep the Master logo on the layout grid and usually in a corner.
- In product chrome, use a responsive SVG that switches between Master and Small logo rather than separate recreated artwork.
- The Small logo line must remain solid white, with unchanged size, no trademark symbol, and official colorways only.

## Responsive Grids

- Use a mobile-first grid model: container, row, column, content.
- Use 12 columns as the base grid.
- Use OUDS Web breakpoints when translating responsive layouts: `2xs`, `xs`, `sm`, `md`, `lg`, `xl`, `2xl`/`xxl`, and `3xl`.
- Use responsive container padding derived from OUDS Web: 16, 24, 28, 32, 40, 56, 80, and 112px across increasing breakpoints.
- Use grid gutters derived from OUDS Web: 8, 16, 24, 32, and 40px across increasing breakpoints.
- Use columns in multiples of 3 on smaller breakpoints (`2xs`, `xs`, `sm`) and multiples of 2 on medium and larger breakpoints where possible.
- Prefer `ColumnSpacing`, `RowSpacing`, layout margins, or framework grid gaps over per-control margins.
- For desktop productivity tools, keep dense repeated controls aligned to the grid and allow lower-priority panels to stack below the main workflow on narrow widths.

## Data Display And Charts

- Prefer ODS Charts for web work and use Apache ECharts with the ODS Charts theme manager when implementing chart behavior.
- Prefer SVG rendering for ECharts when possible.
- Use charts to reveal trend, comparison, relationship, or part-to-whole meaning. Do not use a chart when a short table or KPI summary is clearer.
- Use line charts for continuous values over time.
- Use multiple line charts only when users need to compare several time series.
- Use bar charts to compare related data sets.
- Use stacked bars for proportional contribution within categories.
- Use bar plus line charts for two related metrics where quantity and trend need to be shown together.
- Use pie charts only for simple part-to-whole relationships with few categories; prefer donut charts when the total value needs to be shown in the center.
- Avoid relying on color alone. Add direct labels, legends, tooltips, or a companion data table where needed.
- Use Orange supporting colors for data display, but keep the interface itself dominated by black, white, and neutral surfaces.
- Do not overuse orange in charts. Reserve Orange for brand, focus, or a specific highlighted series.

## Data Grids And Tables

- Use table or data grid patterns for exact values, comparison, audit logs, row selection, and workbook-like data.
- Keep tables accessible: use column or row scopes, captions or clear accessible labels, and a region role for important tables.
- Prefer compact table density for operational tools. In Boosted web, combine `.table` with `.table-sm` for the Orange-recommended row height.
- Use responsive wrappers for overflow rather than shrinking text below readable sizes.
- Use striped rows or striped columns, not both in the same table.
- Avoid colored table variants inherited from generic Bootstrap; they do not match Orange Design System.
- Use contextual dark mode on tables when the surrounding surface is dark.
- For selectable rows, include a checkbox column and accessible labels such as `Select all` and `Select row`.
- For icons or status glyphs in cells, include hidden text or adjacent text so meaning is not color-only.

## Validation And Error States

- Show validation inline near the field or affected control.
- Do not use browser-default validation feedback as the design source; follow Boosted/Orange validation behavior.
- Use invalid feedback for errors and avoid visually displaying valid feedback unless the workflow genuinely requires confirmation.
- Use an icon or text indicator with error/success status; do not rely on color alone.
- Keep labels stable. Validation should change the control border, feedback row, and status text without changing layout dramatically.
- Preserve strong focus state even when a field is invalid.
- Use color-mode adaptive validation tokens for dark mode.
- For recoverable workflow errors, prefer an inline status/result panel or InfoBar over a modal dialog.

## Command Bars And Toolbars

- Use command bars for repeated page-level or table-level actions such as `Run`, `Clear`, `Export`, `Compare`, `Refresh`, and row-selection commands.
- Group related commands. Use explicit accessible labels for button groups and toolbars.
- In Boosted web, use `role="group"` for grouped buttons and `role="toolbar"` for button toolbars.
- Use the secondary outline style for grouped toolbar buttons. Do not mix colored button backgrounds inside a button group.
- Keep destructive actions separated from primary workflow actions and use danger/error styling.
- On narrow layouts, stack or wrap command groups instead of squeezing labels.
- Keep primary action placement predictable: end-aligned in headers/toolbars or first in a focused action row, matching the local app pattern.

## Dark Mode Tokens

- Treat light mode as the default. Add dark mode through semantic aliases rather than rewriting every component.
- Follow Boosted contextual dark mode behavior conceptually: a dark theme can apply globally or to a specific component subtree.
- Use dark semantic tokens for surface, panel, subtle panel, border, text, accent, and focus.
- Use white primary text on near-black surfaces.
- Use darker neutral surfaces for panels and keep borders visible.
- Use Orange as accent/focus in dark mode, not as a dominant background.
- Ensure validation tokens adapt in dark mode and keep error/success states readable.
- For Boosted web, prefer `data-bs-theme="dark"` on the root or parent component. For WinUI/PySide6, mirror this with app-level theme state and semantic tokens.
