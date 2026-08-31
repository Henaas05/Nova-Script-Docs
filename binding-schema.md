# Binding schema

Every button carries an `action` object with this shape:

```json
{
  "type": "clientEvent | serverEvent | toggleVisibility | refreshData | goToPage | none",
  "eventName": "shop:open",
  "payload": "'clothing', 3",
  "targetId": "el_4",
  "targetPageId": "page_2"
}
```

* `type` — which of the six action kinds this is. See [Actions & events](../editor/actions-and-events.md).
* `eventName` — used by `clientEvent`/`serverEvent` only.
* `payload` — a comma-separated value list, written like a Lua/JS argument list (e.g.
  `'clothing', 3`). Parsed at export/test time into a real array; accepts strings, numbers,
  booleans, and nested arrays/objects.
* `targetId` — used by `toggleVisibility`; the id of the element to show/hide.
* `targetPageId` — used by `goToPage`; the id of the page to switch to.

### Data tokens

A `{token}` like `{player.name}` is a flat string key. At runtime, the exported bundle collects
every token used across the design, asks the server (via the generated `fetchData` flow) for
values for all of them at once, and substitutes them into text/placeholder content wherever they
appear — including individual rows of a List element.
