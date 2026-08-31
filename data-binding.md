# Data binding

Type a token like `{player.name}` into any Text, Input placeholder, or List row, and the
**Data** panel in the left sidebar picks it up automatically — type a sample value there for
design-time preview.

### Registering a real data source

Register a provider server-side, either in this resource or from any other:

```lua
exports['nuicreator']:RegisterDataSource('player.money', function(src)
    local Player = QBCore.Functions.GetPlayer(src)
    return Player and Player.PlayerData.money.cash or 0
end)
```

The provider function receives the player's server id and returns whatever value should replace
the token.

### Built-in demo sources

`server.lua` ships with several no-framework examples so you can see the range of what's
fetchable, all using plain FiveM natives:

* `player.name`, `player.ping`, `player.health`, `player.armor`, `player.coords`
* `server.playerCount`, `server.time`

Only `player.money` needs a real framework hookup, since "money" isn't a native FiveM concept —
it's still registered as a demo, returning a placeholder string until you wire it up.

### Fetching live values while designing

Click **↻ Fetch live values** in the Data panel to pull real values from your registered sources
right into the editor's preview — useful for confirming a data source actually works before you
export.

### Refreshing at runtime

A button's action can be **Refresh data**, which re-fetches every `{token}` on the page and
updates the text on screen — useful for something like a "refresh balance" button after a
purchase.

{% hint style="info" %}
A token is currently a flat string key — the provider function must return the final display
value itself. There's no automatic `{player.job.label}`-style traversal into a returned object;
every distinct piece of info needs its own `RegisterDataSource` call.
{% endhint %}
