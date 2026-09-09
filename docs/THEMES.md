# Themes

The site ships with four color themes and four full style themes.

## Included themes

| Value | Look |
|---|---|
| `burgundy` | Default academic crimson |
| `academic-blue` | Classic academic blue |
| `forest-green` | Oxford green |
| `slate` | Modern slate/black |
| `minimal` | Flat, white, hairline layout |
| `academic-paper` | Cream paper + serif |
| `terminal` | Green-phosphor terminal |
| `pixel` | Retro game console |

## Configuration

```json
"theme": {
  "default": "burgundy",
  "switchable": true,
  "options": [
    "burgundy", "academic-blue", "forest-green", "slate",
    "minimal", "academic-paper", "terminal", "pixel"
  ],
  "stylesheets": {
    "minimal": "assets/themes/minimal.css",
    "academic-paper": "assets/themes/academic-paper.css",
    "terminal": "assets/themes/terminal.css",
    "pixel": "assets/themes/pixel.css"
  },
  "fonts": {
    "terminal": "https://fonts.googleapis.com/css2?family=VT323&display=swap",
    "pixel": "https://fonts.googleapis.com/css2?family=Press+Start+2P&family=VT323&display=swap"
  }
}
```

- `default` is used for new visitors.
- `switchable: true` shows the palette button; visitors can cycle the options.
- Color themes change CSS variables in `assets/css/style.css`.
- Style themes load an extra stylesheet when selected and remove it when not.
- Per-theme fonts load independently, so a slow font never blocks the theme.

## Adding a custom style theme

1. Create `assets/themes/my-theme.css`.
2. Add the theme name to `theme.options`.
3. Register the stylesheet in `theme.stylesheets`.
4. Optionally register a font URL in `theme.fonts`.

The custom stylesheet should scope selectors under
`body[data-theme="my-theme"]` to override base variables and layouts.
