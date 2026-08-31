# Elements

Every menu is built from these nine element types, added from the palette on the left of the
editor.

<figure><img src="../assets/promo2_elements.png" alt="Element library"><figcaption></figcaption></figure>

| Element | What it's for |
|---|---|
| **Box** | A rectangle — panels, backgrounds, containers. |
| **Text** | A text label. Supports `{tokens}`, bold/italic/underline, font, and alignment. |
| **Button** | A clickable element. Can carry an [action](actions-and-events.md). |
| **Input** | A text field. Placeholder text supports `{tokens}`. |
| **Image** | Upload a file (stored as base64 in the project) or paste a URL. |
| **List** | One text row per line, each supporting `{tokens}`. Optionally scrollable. |
| **Video/Embed** | A URL — `.mp4`/`.webm`/`.ogg` renders as `<video>`, anything else as an `<iframe>`. |
| **Line** | A thin colored bar for dividers. Rotate it for angled lines. |
| **Icon** | A Font Awesome icon, picked from a quick-pick grid or typed by class name. |

### Position, size, rotation, scale

Every element has X/Y position, width/height (for Line, these are labeled Length/Thickness),
rotation in degrees, and scale as a percentage. Drag an element to move it, drag its bottom-right
handle to resize it — both respect [snapping](editor-tools.md#snapping) if enabled.

### Layer name

Give an element a custom name in the **Layer name** field at the top of its properties. This
name replaces the generic `type · #id` label in the Layers list.

### Behavior

Any element can be marked as a **drag handle** — see
[Drag handles](editor-tools.md#drag-handles-draggable-menus).

### Icon element details

The Icon element's quick-pick grid covers common icons (star, heart, bell, user, house, gear,
check, x, lock, money, cart, comment). For anything else, type a Font Awesome class directly
(e.g. `fa-solid fa-truck`) — browse the full set at fontawesome.com/search.

{% hint style="warning" %}
Icons load via the Font Awesome CDN, which requires the player's game client to reach the
internet from inside the NUI browser. If a server blocks external requests from NUI, icons won't
render. The CDN link is only added to your exported `index.html` if your design actually uses an
icon.
{% endhint %}
