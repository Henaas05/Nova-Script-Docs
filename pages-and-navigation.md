# Pages & navigation

The tab bar above the canvas lists every page in the project.

* Click **+** to add a new page.
* Click the **✎** icon on a tab to rename it.
* Click the **✕** icon to delete it (you always need at least one page left).
* A button's action can be **Go to page**, which switches the visible page — both live in the
  editor (via **▶ Test this action**) and in the exported runtime.

Each page keeps its own set of elements. Data preview values and the project name are shared
across all pages.

### Draggable menus

Any element can be marked as a **drag handle** in its Behavior section. In the *exported*
version, players can drag the whole menu around the screen by that element — like moving a phone
window. Each page remembers its own dragged position independently.

{% hint style="warning" %}
Drag handles only work in the exported runtime, not as a live preview inside the editor itself —
the editor's own drag system is for positioning individual elements at design time.
{% endhint %}
