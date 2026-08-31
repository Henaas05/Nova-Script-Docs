# The launcher

Running `/nuicreator` opens a project picker first — not the editor directly.

<figure><img src="../assets/editor_mockup.png" alt="Editor and launcher"><figcaption></figcaption></figure>

### Creating a project

Type a name in the **+ Create** field and press the button. You land in the editor with a blank
canvas and one empty page.

### Opening a project

Click **Open** next to any project in the list to load it straight into the editor.

### Deleting a project

Click the **✕** next to a project, then confirm. FiveM's Lua sandbox has no file-delete native,
so under the hood the project's `.json` file is overwritten empty and removed from the index
rather than actually deleted from disk — it just disappears from the list, which is all that
matters in practice.

### Going back to the launcher

The **Projects** button in the editor's topbar takes you back to this screen at any point.
Unsaved changes in the current project are **not** auto-saved when you do that — hit **Save**
first if it matters.

### Standalone / browser mode

If you open `html/editor.html` directly in a normal browser (outside FiveM), the launcher lists
whatever is saved in the browser's `localStorage` instead of the server's project files. This is
useful for quickly previewing changes without a running FiveM server.
