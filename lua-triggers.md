# Lua-controlled visibility

Any element can have a **Lua trigger**: an event name, an action (Show / Hide / Toggle), and
whether it should start hidden. Unlike a button's action, this isn't tied to a click — it's
triggered by your own server-side Lua code, which makes it fit things like:

* Showing a notification badge when the player receives a message
* Revealing a panel when a job event fires
* Hiding an element after some condition changes

### How to trigger it

From your own resource — a `RegisterNetEvent` handler, a command, anywhere — call:

```lua
SendNUIMessage({ action = 'trigger', eventName = 'playerGotMessage' })
```

Every element registered against `playerGotMessage` reacts immediately.

### Finding the exact calls to make

The exported `client.lua` snippet lists the exact `SendNUIMessage` call for every trigger your
design actually uses, so you don't have to guess the event names.

### Previewing

Use **▶ Simulate trigger** in the properties panel to preview the effect while designing, without
needing a real event to fire.
