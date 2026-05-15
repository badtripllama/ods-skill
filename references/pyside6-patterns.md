# PySide6 Resource Patterns

## Recommended App Structure

```text
app/
  design_system/
    orange_tokens.py
    orange_colors.qss
    orange_typography.qss
    orange_components.qss
  views/
  viewmodels/
```

## Loading QSS

Load design-system QSS once at application startup.

```python
from pathlib import Path

from PySide6.QtWidgets import QApplication


def load_qss(*paths: Path) -> str:
    return "\n\n".join(path.read_text(encoding="utf-8") for path in paths)


app = QApplication([])
app.setStyleSheet(
    load_qss(
        Path("design_system/orange_colors.qss"),
        Path("design_system/orange_typography.qss"),
        Path("design_system/orange_components.qss"),
    )
)
```

## Token Usage

- Keep colors in `orange_tokens.py` for Python-side logic.
- Keep spacing constants in `orange_tokens.py` and apply them through layouts, not QSS.
- Keep visual rules in QSS for widgets.
- Do not hardcode Orange colors directly in widget constructors.
- Prefer object names or semantic classes for special cases:

```python
run_button.setObjectName("primaryButton")
status_label.setProperty("status", "error")
```

## Spacing And Padding

Use token constants for layout spacing:

```python
from design_system.orange_tokens import (
    ODS_PANEL_PADDING,
    ODS_SPACE_12,
    ODS_SPACE_16,
)

layout.setContentsMargins(*ODS_PANEL_PADDING)
layout.setSpacing(ODS_SPACE_16)
toolbar_layout.setSpacing(ODS_SPACE_12)
```

- Use `ODS_PAGE_PADDING` for root windows or full-page views.
- Use `ODS_PANEL_PADDING` for framed workflow groups.
- Use `ODS_CONTROL_PADDING` for custom painted controls when QSS is not enough.
- Use 8px spacing increments for repeated controls.
- Prefer layout margins and spacing over per-widget fixed margins.

## QSS Notes

Qt Style Sheets do not support CSS variables. Duplicate token values only in the design-system QSS files, not across screen code.

Use comments in QSS to preserve the token name next to each value.
