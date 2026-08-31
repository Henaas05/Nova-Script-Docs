# Editor tools

### Undo / redo

`Ctrl+Z` / `Ctrl+Shift+Z`, or the topbar buttons. Snapshots the whole project. Text/number/color
fields get one undo step per edit session (from focus to blur), not one per keystroke, so typing
a whole value doesn't flood the history.

### Copy, paste, duplicate

Select an element and press `Ctrl+C` / `Ctrl+V`, or `Ctrl+D` to duplicate in place, or use the
**⧉ Duplicate** button in the properties panel. Pasted copies get a new id and are offset by
20px so they don't sit exactly on top of the original.

### Multi-select

* **Shift/Ctrl-click** adds or removes individual elements from the selection.
* **Click-and-drag on empty canvas** draws a marquee that selects everything inside it.
* **Ctrl+A** selects every element on the current page.

With more than one element selected, the properties panel shows bulk **Duplicate**/**Delete**
actions, and dragging any selected element moves the whole group together. Grid snap and magnet
alignment are skipped for group moves.

### Find & replace

`Ctrl+F` opens a modal that searches text, placeholders, and list items across every page.
**Find next** jumps to and selects each match; **Replace all** applies everywhere at once.

### Layers panel

Each layer row shows the element's [name](elements.md#layer-name) (or a generic label), and:

* **Drag the row** (via the `⋮⋮` grip) to reorder layers — this changes stacking order, both in
  the editor and the export.
* Click the **eye icon** to hide a layer. A hidden layer is skipped when rendering the canvas
  (though still selectable/editable from this list) and is **excluded entirely from the
  export** — see [Known limitations](../reference/known-limitations.md) for how this differs
  from a Lua trigger's "starts hidden."
* Click the **✕** to delete the element.

### Snapping

In Settings (⚙): **Snap to pixel grid** (24px) and **Snap to elements (magnet)** — the latter
snaps to other elements' edges/centers and shows a visible guide line while dragging. Both toggle
independently.

### Rulers

Toggle **Show rulers** in Settings to display pixel rulers along the top and left of the canvas.

### Zoom

Zoom in/out buttons in the topbar, `Ctrl` + scroll wheel, or `Ctrl +` / `Ctrl -` / `Ctrl 0` to
reset to 100%.

{% hint style="warning" %}
Zoom scales the canvas visually via a CSS transform, which doesn't affect layout size. Zooming in
past 100% on a design bigger than the canvas viewport can push content out of scroll range —
you won't be able to scroll to reach it. Rulers and the background grid don't scale with zoom
(cosmetic only).
{% endhint %}

### Minimize / Show-Hide UI

**Minimize UI** (in Settings) hides the side panels for more canvas room. The eye icon in the
topbar toggles **Show/Hide UI** entirely, hiding all editor chrome for a clean preview — click
the floating "Show UI" button to bring it back.
