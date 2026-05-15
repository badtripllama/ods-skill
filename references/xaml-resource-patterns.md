# XAML Resource Patterns

## Recommended App Structure

```text
src/AppName/
  DesignSystem/
    OrangeColors.xaml
    OrangeSpacing.xaml
    OrangeTypography.xaml
    OrangeButtons.xaml
    OrangeTextInputs.xaml
    OrangeWindowLayout.xaml
  Views/
  ViewModels/
```

## App.xaml Merge Order

Merge base WinUI resources first, then tokens, then component styles.

```xml
<ResourceDictionary.MergedDictionaries>
    <XamlControlsResources xmlns="using:Microsoft.UI.Xaml.Controls" />
    <ResourceDictionary Source="DesignSystem/OrangeColors.xaml" />
    <ResourceDictionary Source="DesignSystem/OrangeSpacing.xaml" />
    <ResourceDictionary Source="DesignSystem/OrangeTypography.xaml" />
    <ResourceDictionary Source="DesignSystem/OrangeButtons.xaml" />
    <ResourceDictionary Source="DesignSystem/OrangeTextInputs.xaml" />
    <ResourceDictionary Source="DesignSystem/OrangeInfoBars.xaml" />
    <ResourceDictionary Source="DesignSystem/OrangeWindowLayout.xaml" />
</ResourceDictionary.MergedDictionaries>
```

## Naming Rules

- Prefix reusable app resources with `Ods`.
- Use semantic names: `OdsPrimaryBrush`, `OdsPanelPadding`, `OdsPrimaryButtonStyle`.
- Avoid names tied to one screen unless the style is local to that screen.

## View Rules

- Use tokens in views:

```xml
<Grid Padding="{StaticResource OdsPagePadding}">
```

- Use spacing tokens for layout rhythm:

```xml
<Grid ColumnSpacing="{StaticResource OdsSpace20}" RowSpacing="{StaticResource OdsSpace16}">
```

- Avoid inline values when a token exists:

```xml
<!-- Avoid -->
<Border Padding="18" Background="#FFFFFF" />
```

```xml
<!-- Prefer -->
<Border Padding="{StaticResource OdsPanelPadding}" Background="{StaticResource OdsPanelBrush}" />
```

- Use `OdsSectionMargin` only when separating major workflow blocks. Prefer `RowSpacing` or `ColumnSpacing` for repeated form fields and panels.

## Validation Pattern

Use inline result/status panels for recoverable errors. Use dialogs only when the user must make a blocking decision.
