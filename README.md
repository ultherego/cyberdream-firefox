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

Install it from
[addons.mozilla.org](https://addons.mozilla.org/firefox/addon/cyberdream-green/),
where it is listed as **cyberdream green**.

### Try it from source

1. Open `about:debugging#/runtime/this-firefox`.
2. Click **Load Temporary Add-on…** and pick `manifest.json`.

The theme stays until Firefox is restarted.

### Build the package

```sh
zip -j cyberdream.xpi manifest.json
```

Release builds of Firefox only install signed add-ons, so a package you build
yourself has to be signed through
[addons.mozilla.org](https://addons.mozilla.org/developers/) under your own
add-on ID before it can be installed from `about:addons`.

## Optional extras

A theme can only set colors. The `extras/` folder holds two stylesheets for
what it cannot reach:

- `cyberdream-chrome.css` – square corners in the interface (tabs, address
  bar, menus) and a darker hover color for tabs.
- `cyberdream-content.css` – square corners on built-in pages such as the
  settings.

They are not part of the add-on. To use them:

1. Set `toolkit.legacyUserProfileCustomizations.stylesheets` to `true` in
   `about:config`.
2. Open `about:support`, find **Profile Directory** and create a `chrome`
   folder inside it.
3. Copy both files into that `chrome` folder.
4. Put `@import url("cyberdream-chrome.css");` at the very top of
   `chrome/userChrome.css` and `@import url("cyberdream-content.css");` at the
   very top of `chrome/userContent.css`. Create the files if they do not exist.
5. Restart Firefox.

These stylesheets depend on Firefox internals and may need updating after a
Firefox release. They were written against Firefox 160.

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
