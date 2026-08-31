# NUI Creator

**NUI Creator** is an in-game visual editor for building FiveM NUI interfaces. Drag out boxes,
text, buttons, images, icons and more onto a canvas, style them, wire buttons to real
client/server events, pull in live data from your server, and export a ready-to-use code bundle
— all without writing HTML or CSS by hand.

<figure><img src="assets/promo1_hero.png" alt="NUI Creator hero"><figcaption></figcaption></figure>

## What you get

* A drag-and-drop canvas that runs **inside the game**, with snapping, rulers, zoom, and
  multi-select
* Nine element types: Box, Text, Button, Input, Image, List, Video/Embed, Line, and Icon
  (Font Awesome)
* Full styling: colors, gradients, transparency, borders, shadows, hover effects, and entrance
  animations
* Live event binding — test a button's client/server event right inside the editor before you
  export
* Data binding — show `{player.name}`, `{player.money}`, or anything else your server registers
* A one-click **Export** that generates `index.html`, `style.css`, `runtime.js`, and the Lua
  snippets that wire it all together

## Where to start

New to NUI Creator? Start with [Installation](getting-started/installation.md), then
[The launcher](getting-started/launcher.md) to see how projects are organized, then
[Your first menu](getting-started/first-menu.md) for a walkthrough.

Already installed? Jump straight to the [Editor Guide](editor/elements.md) or
[Exporting](export/export-bundle.md).

{% hint style="warning" %}
Read [Known limitations](reference/known-limitations.md) before you rely on this in production —
it lists what has and hasn't been tested, and a few things that are still rough edges.
{% endhint %}
