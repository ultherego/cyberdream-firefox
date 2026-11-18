# cyberdream for Firefox

A dark, high-contrast Firefox theme in the [cyberdream](https://github.com/scottmckendry/cyberdream.nvim)
palette. The active tab is marked with a green outline and a grey fill. It
works with both horizontal and vertical tabs.

It is a plain static theme: one `manifest.json`, no scripts, no permissions.

## Palette

| Role                           | Color     |
| ------------------------------ | --------- |
| Window, toolbar, menus         | `#16181a` |
| Address bar, sidebar           | `#111214` |
| New tab cards                  | `#1e2124` |
| Borders                        | `#3c4048` |
| Active tab background          | `#242627` |
| Text and icons                 | `#ffffff` |
| Address bar text               | `#7b8496` |
| Accent (active tab outline, focus) | `#5eff6c` |
| Selected address bar result    | `#213b26` |
| Selected sidebar item          | `#264b2c` |

## Install

### Try it without installing

1. Open `about:debugging#/runtime/this-firefox`.
2. Click **Load Temporary Add-on…** and pick `manifest.json`.

The theme stays until Firefox is restarted.

### Build an installable package

```sh
zip -j cyberdream.xpi manifest.json
```

Release builds of Firefox only install signed add-ons, so sign the package
through [addons.mozilla.org](https://addons.mozilla.org/developers/) (listed
or self-distributed) before installing it from `about:addons`.

## Customizing

All colors live in the `theme.colors` table of `manifest.json`. To change the
active tab highlight, edit `tab_line` (outline) and `tab_selected`
(background). The keys are documented on
[MDN](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/theme).

## Credits

Colors come from [cyberdream.nvim](https://github.com/scottmckendry/cyberdream.nvim)
by Scott McKendry (MIT).

## License

[MIT](LICENSE)
