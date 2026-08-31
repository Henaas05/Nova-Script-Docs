# Your first menu

The fastest way to see everything working together is to load the built-in demo.

1. Open `/nuicreator` and either create a new project or, once inside the editor, click
   **Preset** in the topbar to load the `shop_menu` demo.
2. The demo is a two-page clothing shop: a main page with a search box, a **Buy** button bound to
   a `serverEvent`, a **Close** button, and a balance display using `{player.money}`; a second
   page shown via a **Go to page** button, with a **Back** button returning to the first page.
3. Click any element to select it — the properties panel on the right shows everything about it:
   position, style, animation, and (for buttons) its action.
4. Click **▶ Test this action** on the **Buy** button. If you're in FiveM, this fires the real
   `shop:buyItem` server event — check your server console.
5. Click **Export** in the topbar. The modal shows five files:
   `index.html`, `style.css`, `runtime.js`, a `client.lua` snippet, and a `server.lua` snippet.
   These are what you'd copy into your own resource to actually ship this menu.

From here, see the [Editor Guide](../editor/elements.md) for everything you can build with, or
[Exporting](../export/export-bundle.md) for what happens when you click Export.
