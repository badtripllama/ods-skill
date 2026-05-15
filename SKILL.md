---
name: ods-skill
description: Orange Design System guidance based primarily on Orange web, OUDS Web, Boosted, and ODS Charts sources, with reusable WinUI XAML and Python PySide6 templates. Use when Codex builds or modifies Orange-branded WinUI or PySide6 frontends, app windows, forms, buttons, spacing, typography, logos, responsive grids, validation states, data tables, charts, command bars, dark mode, workflow screens, or xlengine UI.
---

# Orange Design System

Use this skill to build WinUI or Python PySide6 interfaces that follow Orange web/OUDS design rules and reusable UI patterns.

## Core Workflow

1. Read the repo UI context first: active views/windows, existing style resources, and any design docs.
2. If `docs/design-system/` or `DesignSystem/` exists in the target repo, treat those files as the source of truth.
3. Identify the target framework:
   - WinUI: use XAML `ResourceDictionary` files.
   - PySide6: use QSS files and `orange_tokens.py`.
4. Use Orange web, OUDS Web, Boosted, and ODS Charts sources as primary guidance.
5. Use OUDS iOS sparsely and only as a secondary cross-check for platform-neutral tokens or component vocabulary. Do not import SwiftUI, iOS, tvOS, watchOS, or Flutter behavior into WinUI or PySide6 work.
6. If exact Orange tokens are missing, use the templates in `assets/templates/` as a starting point and flag assumptions.
7. Prefer shared tokens and styles over inline colors, margins, fonts, or control templates.
8. Keep workflow screens task-first, dense enough for productivity tools, and consistent across repeated operations.
9. Verify the app builds or starts after UI changes.

## References

Load only what is needed:

- `references/orange-winui-guidelines.md`: layout, spacing, behavior, accessibility, and visual rules.
- `references/orange-web-ods-guidelines.md`: source hierarchy and web-derived rules for logos, responsive grids, charts, data grids, validation, command bars, and dark mode.
- `references/orange-typography.md`: Orange/OUDS typography scale and WinUI mapping.
- `references/xaml-resource-patterns.md`: how to organize WinUI resource dictionaries and apply spacing/templates.
- `references/pyside6-patterns.md`: how to organize PySide6 QSS, layout spacing, and token constants.

## Template Assets

Reusable WinUI starter files live in `assets/templates/`:

- `OrangeColors.xaml`
- `OrangeSpacing.xaml`
- `OrangeTypography.xaml`
- `OrangeButtons.xaml`
- `OrangeTextInputs.xaml`
- `OrangeInfoBars.xaml`
- `OrangeWindowLayout.xaml`

Reusable PySide6 starter files live in `assets/templates/pyside6/`:

- `orange_tokens.py`
- `orange_colors.qss`
- `orange_typography.qss`
- `orange_components.qss`

Copy or adapt these into the target app instead of retyping styles from memory.

## Guardrails

- Do not invent new colors when a token exists.
- Do not use iOS, tvOS, watchOS, Android, or Flutter guidance when a web/OUDS Web/Boosted source exists.
- Do not hardcode control spacing in views when a spacing token exists.
- Do not create marketing-style screens for operational tools.
- Do not place cards inside cards.
- Do not use rounded corners above 8px unless the local design system says so.
- Do not use emoji.
- Use direct, functional UI text.
