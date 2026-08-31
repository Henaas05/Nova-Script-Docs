# Animations

Every element has an **Animation** section in its properties: type, duration, and delay.

### Animation types

* Fade
* Slide up / down / left / right
* Scale in

### Previewing

Click **▶ Preview animation** to see it play on the canvas immediately, without needing to
trigger it for real.

### When animations play at runtime

An element's animation plays:

* When its page first becomes visible (on load)
* When you navigate to its page via a **Go to page** action
* When it's toggled from hidden to visible (via `toggleVisibility` or a
  [Lua trigger](lua-triggers.md))

### Hover transitions

Hover effects use their own separate **transition duration**, distinct from entrance animations
— see [Styling](styling.md#hover-effect).
