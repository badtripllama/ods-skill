# Orange WinUI Guidelines

## Intent

Build quiet, professional, Orange-branded productivity UI for internal desktop workflows.

The UI should feel operational rather than promotional: clear hierarchy, predictable controls, restrained layout, and strong validation feedback.

## Color Tokens

Use repo tokens first. If no repo tokens exist, start with the OUDS/Orange tokens in `assets/templates/OrangeColors.xaml`.

Source references:

- Orange Design System shared web page: `https://system.design.orange.com/0c1af118d/p/8118d1-web`
- OUDS Web color palette: `https://web.unified-design-system.orange.com/docs/0.5/customize/color-palette/`
- Boosted color guidance: `https://boosted.orange.com/docs/5.0/guidelines/colors/`

Core rule from Orange guidance: Orange is a black, white, and orange brand. In digital interfaces, orange is a highlight or focus color; black and white should dominate.

Core colors:

- Brand orange: `#FF7900`
- Accessible orange: `#F15E00`
- Black: `#000000`
- White: `#FFFFFF`
- Warm gray 100: `#F9F5F0`
- Warm gray 900: `#353228`

Neutral grays:

- Light gray 80: `#F4F4F4`
- Light gray 160: `#EEEEEE`
- Light gray 240: `#E0E0E0`
- Light gray 320: `#D6D6D6`
- Light gray 400: `#CCCCCC`
- Light gray 800: `#999999`
- Light gray 960: `#858585`
- Dark gray 240: `#666666`
- Dark gray 320: `#5C5C5C`
- Dark gray 400: `#555555`
- Dark gray 640: `#333333`
- Dark gray 720: `#272727`
- Dark gray 800: `#1F1F1F`
- Dark gray 880: `#141414`

Functional colors:

- Success: `#3DE35A`
- Success dark: `#0A4715`
- Error: `#DB0002`
- Error dark: `#800001`
- Info: `#26B2FF`
- Info dark: `#003857`
- Warning: `#FFD000`
- Warning dark: `#3D3100`

Decorative colors:

- Sky: `#4AB4E6`
- Emerald: `#50BE87`
- Amber: `#FFB400`
- Amethyst: `#A885D8`
- Pink: `#FFB4E6`

WinUI semantic mapping:

- `OdsAccentBrush`: accessible orange `#F15E00`
- `OdsBrandOrangeBrush`: brand orange `#FF7900`
- `OdsSurfaceBrush`: light gray 80 `#F4F4F4`
- `OdsPanelBrush`: white `#FFFFFF`
- `OdsBorderBrush`: light gray 400 `#CCCCCC`
- `OdsTextPrimaryBrush`: black `#000000`
- `OdsTextSecondaryBrush`: dark gray 240 `#666666`
- `OdsFocusBrush`: accessible orange `#F15E00`

## Layout Rules

- Put the user's primary workflow decision first.
- Keep desktop workflows scan-friendly: left setup, center status/preview, right results/audit is acceptable.
- Use 8px spacing increments.
- Use 24px to 32px page padding.
- Use 16px to 20px panel padding.
- Use square corners for cards, panels, buttons, and inputs by default. Keep `OdsPanelCornerRadius` and `OdsControlCornerRadius` at `0` unless the target app has an explicit local design-system token for rounded corners.
- Avoid nested panels unless there is a real grouping need.
- Use full-width bands or grids for major regions.

## Spacing And Padding Structure

Use these defaults unless the target app already defines stricter tokens:

- `OdsPagePadding`: outer page or root view padding, 28px.
- `OdsPanelPadding`: bordered panel or workflow group padding, 18px.
- `OdsControlPadding`: button and compact input padding, 12px horizontal and 8px vertical.
- `OdsSectionMargin`: vertical separation between major workflow sections, 24px top.
- `OdsSpace4`: tight icon or helper-text gap.
- `OdsSpace8`: default gap between label, helper text, and compact related controls.
- `OdsSpace12`: gap inside compact toolbar or control rows.
- `OdsSpace16`: default gap between fields in a form group.
- `OdsSpace20`: gap between panels inside dense desktop tools.
- `OdsSpace24`: gap between major rows or workflow regions.
- `OdsSpace32`: large separation for page-level groups.

Prefer grid `ColumnSpacing` and `RowSpacing` for layout rhythm. Use margins only for deliberate section separation.

## Control Rules

- Primary button: use Orange fill with black or white foreground based on contrast.
- Secondary button: neutral background, visible border.
- Destructive actions: do not use Orange; use error color.
- Text inputs must have clear labels.
- Optional fields should be visibly optional through label or helper text when needed.
- Operation selection should be first for workflow-driven tools.
- Show status and validation inline before using dialogs.

## Accessibility

- Preserve keyboard focus visuals.
- Do not rely on color alone for errors.
- Keep text readable at default Windows scaling.
- Use minimum 32px control height for dense desktop forms.
- Use clear button labels: `Run`, `Clear`, `Compare`, `Export`.

## WinUI Notes

- Prefer `ResourceDictionary` styles over inline XAML.
- Keep `MainWindow.xaml` minimal and put screen content in views.
- Use MVVM bindings for state and commands.
- Use `ContentDialog` only for blocking confirmation or severe errors.
- Use `InfoBar` or results panel for normal warnings and validation feedback.
