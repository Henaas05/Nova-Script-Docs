# Wiring it into your resource

1. Create (or open) the resource that should own this NUI page.
2. Copy `index.html`, `style.css`, and `runtime.js` from the export modal into that resource's
   `html/` folder (or wherever your `ui_page` points).
3. Make sure your `fxmanifest.lua` has:
   ```lua
   ui_page 'html/index.html'
   files {
       'html/index.html',
       'html/style.css',
       'html/runtime.js'
   }
   ```
4. Paste the **client.lua snippet** into your resource's client-side Lua. It already contains
   everything needed to forward button actions and `{token}` lookups — no editing required
   unless you want to change event names.
5. Paste the **server.lua snippet** into your resource's server-side Lua. Fill in the
   auto-generated stubs — replace each `return nil` with your actual lookup (a framework call,
   a native, a database query).
6. Open/close the NUI the way you normally would (`SetNuiFocus` + `SendNUIMessage`, or however
   your resource already manages its UI).

### Registering data sources from elsewhere

You don't have to paste the `RegisterDataSource` calls into the same resource — any resource can
register a source for this one's tokens:

```lua
exports['your-nui-resource-name']:RegisterDataSource('player.money', function(src)
    local Player = QBCore.Functions.GetPlayer(src)
    return Player and Player.PlayerData.money.cash or 0
end)
```

### Triggering Lua-controlled visibility

Call the exact `SendNUIMessage({ action = 'trigger', eventName = '...' })` line shown in your
`client.lua` snippet from wherever the real event happens in your own code.
