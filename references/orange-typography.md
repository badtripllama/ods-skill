# Orange Typography

Source references:

- Orange Design System shared web page: `https://system.design.orange.com/0c1af118d/p/8118d1-web`
- OUDS Web typography: `https://web.unified-design-system.orange.com/orange/docs/0.6/content/typography/`
- Boosted typography: `https://boosted.orange.com/docs/5.0/content/typography/`
- Boosted typography guidelines: `https://boosted.orange.com/docs/5.0/guidelines/typography/`

## Principles

- Use the platform/native font stack for accessibility and OS consistency.
- Base text should be 16px.
- Headings and display headings are bold.
- Body text should stay regular; use bold mainly for headings, labels, and explicit emphasis.
- Keep letter spacing at zero in WinUI templates unless the project explicitly approves otherwise.
- Do not scale font size by viewport width.

## Font Stack

For WinUI desktop apps, use:

```text
Segoe UI, Helvetica Neue, Helvetica, Arial
```

This follows OUDS native-font-stack guidance while fitting Windows desktop UI conventions.

## Desktop Type Scale

Use these desktop values as the base WinUI scale:

| Token | Size | Weight | Line Height |
| --- | ---: | --- | ---: |
| Display 1 | 60 | Bold | 60 |
| Display 2 | 50 | Bold | 50 |
| Display 3 | 40 | Bold | 40 |
| Display 4 | 34 | Bold | 34 |
| Heading 1 | 34 | Bold | 34 |
| Heading 2 | 30 | Bold | 32 |
| Heading 3 | 24 | Bold | 26 |
| Heading 4 | 20 | Bold | 22 |
| Heading 5 | 18 | Bold | 20 |
| Heading 6 | 16 | Bold | 18 |
| Lead | 20 | Regular | 30 |
| Body | 16 | Regular | 24 |
| Small | 14 | Regular | 16 |

## WinUI Usage

- Use `OdsPageTitleTextBlockStyle` for screen titles.
- Use `OdsSectionTitleTextBlockStyle` for panel and section headings.
- Use `OdsBodyTextBlockStyle` for normal text.
- Use `OdsSmallTextBlockStyle` for metadata, helper text, and compact audit rows.
- Use `OdsMutedTextBlockStyle` only for secondary text.

## Operational Desktop Guidance

For dense internal tools, prefer heading sizes over display sizes. Reserve display styles for splash screens, large empty states, or very high-level pages.
