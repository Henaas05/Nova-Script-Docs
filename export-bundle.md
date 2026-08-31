# The export bundle

<figure><img src="../assets/promo5_export.png" alt="Export"><figcaption></figcaption></figure>

Clicking **Export** opens a modal with five tabs — each is a complete file, with a **Copy this
file** button.

| File | What it is |
|---|---|
| `index.html` | Static markup — one element per `<div>`/`<button>`/`<input>`, absolute-positioned, grouped into per-page containers. |
| `style.css` | The styles you set in the properties panel, plus the fixed page/animation/keyframe rules. |
| `runtime.js` | A **fixed, generic** file — identical every export — that reads the embedded `BINDINGS`/`DATA_BINDINGS`/`ANIMATIONS`/`TRIGGERS` objects, wires up clicks, resolves `{tokens}`, switches pages, and handles drag handles and Lua triggers. |
| `client.lua` snippet | Forwards button clicks and `{token}` lookups between the NUI and the server. Also lists the exact `SendNUIMessage` calls for any Lua triggers your design uses. |
| `server.lua` snippet | The `RegisterDataSource` registry and resolver (auto-generated, no editing needed), plus **one auto-generated stub per `{token}` your design uses** — only the `return nil` line inside each stub needs to become a real lookup. |

### Why testing in the editor matches the export

The exported runtime and the editor's own **Test**/**Fetch live values**/**Simulate trigger**
buttons all funnel through the same `type`/`eventName`/`payload` and `{token}` shapes. What you
test in the editor behaves identically once exported — there's no separate code path to get out
of sync.

### Hidden layers are excluded

If you've hidden any layers (see [Editor tools](../editor/editor-tools.md#layers-panel)), they
don't appear anywhere in the export — not in the HTML, CSS, bindings, or data tokens.
