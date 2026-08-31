# Styling

<figure><img src="../assets/promo4_styling.png" alt="Styling features"><figcaption></figcaption></figure>

### Colors & transparency

Every element has a Background color and, for text-capable elements, a Text color. Next to
Background is a **Background opacity %** field — under 100% it renders as `rgba()` instead of a
flat hex color, both live in the editor and in the export.

### Gradient backgrounds

Toggle **Gradient background** in the Decorative section to replace the flat background with a
two-color linear gradient at any angle.

### Border

Border style (none/solid/dashed/dotted), width, and color are separate fields — set style to
`none` to hide the border entirely.

### Drop shadow

Toggle **Drop shadow** for a soft shadow with configurable color and blur.

### Text formatting

Available on Text, Button, and List: bold, italic, underline toggles, a font picker, text
alignment (left/center/right), and line height.

### Hover effect

Any element can have a hover background/text/border color and a scale bump, with its own
transition duration. This is **previewed live in the editor** — a `<style>` tag is injected
behind the scenes so real CSS `:hover` works even though the element's base styles are set
inline — and exported as plain CSS `:hover` rules, so no JavaScript runs at click-time for this
part.
