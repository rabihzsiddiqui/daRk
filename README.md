# daRk.

daRk is a single-file OLED burn-in helper. It shows a minimal landing page, then switches to a pure black fullscreen when you click **go daRk**.

## Why These Mitigations Exist

- Pure black (`#000000`) turns OLED pixels off or nearly off, reducing emitter wear while the screen stays awake.
- Fullscreen hides browser UI so bright static bars, tabs, and controls are not left on the display.
- The hidden cursor prevents a small static pointer shape from sitting on the panel.
- Screen Wake Lock asks the browser to keep the display awake while the black screen is active.
- A 1px nearly-black drifting dot keeps at least one pixel changing slowly, reducing the chance of any leftover static-pixel pattern.
- Escape or click exits the mode, releases Wake Lock, restores the cursor, and returns to the landing page.

Wake Lock support depends on the browser. If the browser releases it, daRk tries to re-acquire it when the tab becomes visible again.

## Run Locally

From this folder:

```sh
python3 -m http.server
```

Then open:

```text
http://localhost:8000
```
