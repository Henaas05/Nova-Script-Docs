# Installation

1. Drop the `nui-creator` folder into your server's `resources/` directory. You can rename the
   folder if you like — nothing depends on the folder being named exactly `nui-creator`.
2. Add the following to your `server.cfg`:
   ```
   ensure nuicreator
   ```
3. By default, **anyone who can run `/nuicreator` can also save, load, and delete projects.** If
   you want to restrict that to specific staff, open `server.lua` and change the `canUseEditor`
   function:
   ```lua
   local function canUseEditor(src)
       return IsPlayerAceAllowed(src, 'nuicreator.use')
   end
   ```
   Then add the permission in `server.cfg`:
   ```
   add_principal identifier.license:xxxxxxx group.nuicreator
   add_ace group.nuicreator nuicreator.use allow
   ```
4. Restart the resource (or your server), then in-game run:
   ```
   /nuicreator
   ```

This opens the [launcher](launcher.md) — a project picker, not the editor itself.

{% hint style="info" %}
If `/nuicreator` opens but saving or loading a project silently does nothing, double-check step 3
— that's almost always a permissions issue.
{% endhint %}
