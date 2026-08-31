# Known limitations

An honest list of what to be aware of.

### Data binding

* A `{token}` is a flat string key — there's no automatic `{player.job.label}`-style traversal
  into a returned object. Every distinct piece of info needs its own `RegisterDataSource` call.

### Zoom

* Zoom scales the canvas via a CSS transform, which doesn't affect layout size. Zooming in past
  100% on a design bigger than the canvas viewport can push content out of scroll range.
* Rulers and the background grid don't visually scale with zoom (cosmetic only).

### Hidden layers vs. Lua triggers

* Hiding a layer (via the eye icon) **excludes it from the export entirely** — it's a "not part
  of this design right now" toggle.
* A [Lua trigger](../editor/lua-triggers.md) set to "start hidden" **does** ship in the export,
  just invisible until triggered.
* These are two different mechanisms — don't expect a hidden layer to reappear via a Lua trigger.

### Drag handles

* Only work in the exported runtime, not as a live preview inside the editor — the editor's own
  drag system is for positioning individual elements at design time.

### Multi-select group moves

* Grid snap and magnet alignment are skipped when dragging a multi-selected group, to keep the
  interaction simple.

### Icons

* The Icon element loads Font Awesome via CDN, which requires the player's client to reach the
  internet from inside the NUI browser. If external requests are blocked on a given server,
  icons won't render.

### Permissions

* By default, anyone who can run `/nuicreator` can also save/load/delete projects. See
  [Installation](../getting-started/installation.md) for how to restrict that with an ACE
  permission.

### Testing coverage

* The core logic — project migration and the export bundle generator — is covered by automated
  test scripts run during development, which caught and fixed two real bugs (a broken payload
  parser, and List rows not being wired into the data-binding export).
* The visual/interactive side (drag, resize, hover preview, rulers, zoom) has been tested in a
  live FiveM client and had several real bugs found and fixed there too — see the
  [Changelog](changelog.md) for specifics — but hasn't been exhaustively tested across every
  FiveM server configuration.
