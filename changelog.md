# Changelog

Notable fixes found through testing, in case you're troubleshooting similar symptoms.

### Fixes from real in-game testing

* **Save/load/delete/list did nothing, silently.** Every one of those operations was gated
  behind an ACE permission (`nuicreator.use`) that wasn't set up anywhere by default, and failed
  with zero feedback. `canUseEditor()` now defaults to allowing everyone; every failure path now
  sends an actual error message to the NUI, shown in the console panel — and the launcher's
  project list shows an error instead of hanging on "Loading…" if the server never responds.
* **Pages couldn't be renamed.** A single click on a page tab re-rendered the whole tab bar,
  destroying the DOM node mid-gesture before a second click could register as a double-click.
  Clicking an already-active tab is now a no-op, and there's a dedicated ✎ rename button that
  doesn't depend on double-click timing at all.
* **Elements couldn't be renamed.** Added a "Layer name" field to the properties panel.
* **The Line element was effectively unresizable.** Default thickness was 2px, making the
  resize handle a near-invisible sliver. Default thickness is now 6px, the handle is bigger, and
  Line's size fields are relabeled "Length"/"Thickness" as a guaranteed-to-work fallback.
* **Added zoom.** In/out buttons, `Ctrl`+scroll, and keyboard shortcuts.
* **Multi-select only moved one element.** Dragging any element in a multi-selection now moves
  the whole group together.

### Fixes from automated testing

* **Button payloads were silently broken.** The parser used `JSON.parse`, which rejects
  single-quoted strings — exactly the format the UI tells you to type (`'clothing', 3`). Every
  payload with a string value silently became an empty array. Fixed by parsing with `Function()`
  instead.
* **List rows with `{tokens}` weren't exported.** They resolved fine in the editor's own preview,
  but were never wired into the exported data-binding system.
