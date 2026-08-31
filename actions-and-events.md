# Actions & events

<figure><img src="../assets/promo3_events.png" alt="Event binding"><figcaption></figcaption></figure>

Any **Button** can carry one action, set in its properties panel:

| Action type | What it does |
|---|---|
| `none` | No action. |
| `clientEvent` | Fires `TriggerEvent(eventName, ...payload)` on the client. |
| `serverEvent` | Fires `TriggerServerEvent(eventName, ...payload)` to the server. |
| `toggleVisibility` | Shows/hides another element on the same page. |
| `refreshData` | Re-fetches every `{token}` on the page — see [Data binding](data-binding.md). |
| `goToPage` | Switches the visible page — see [Pages & navigation](pages-and-navigation.md). |

### Payload

For `clientEvent`/`serverEvent`, the **Payload** field takes a comma-separated list of values,
written the way you'd write them in Lua/JS — for example:

```
'jacket_01', 250
```

This gets parsed into an array (`['jacket_01', 250]`) and passed as extra arguments to the
triggered event.

### Testing before you export

Click **▶ Test this action** on a selected button to fire the real event immediately, right from
the editor — useful for confirming your server actually handles it before you ship the menu.
