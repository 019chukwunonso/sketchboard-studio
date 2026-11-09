# Lecture Whiteboard

## What to build
- Turn `/` into a polished, browser-based teaching whiteboard focused on an open writing area that occupies nearly the full screen (target: at least 97% of the viewport area).
- Keep controls in one narrow, top-to-bottom icon column at the extreme left. When the board is active, make the rail translucent so it stays visible without obstructing writing; use simple icons with brief labels on hover/focus to help new users learn them. Keep secondary options compact and out of the writing area.
- Provide freehand drawing for mouse and stylus, selection, erasing, text, common shapes and arrows, undo/redo, zoom and pan, and color/stroke controls.
- Add a presentation view that hides editing controls and uses the browser's full-screen mode when requested. Support saving a drawing locally, reopening it, and exporting it for tutorials.
- Use a restrained Paper & Ink look with Space Grotesk headings and DM Sans labels as sensible defaults; keep the canvas itself bright, uncluttered, and visually dominant.

## Implementation approach
- Embed the Excalidraw React whiteboard as the drawing engine and customize its surrounding controls and visible interface to match the requested open, low-clutter teaching workflow. Excalidraw supports freehand, common diagram tools, undo/redo, zoom, and exports, and is embeddable in React [5](https://github.com/excalidraw/excalidraw/blob/master/README.md).
- Load the editor only in the browser because its integration documentation says it does not support server rendering [4](https://docs.excalidraw.com/docs/@excalidraw/excalidraw/integration).
- Keep drawings in the browser rather than adding accounts or cloud storage; there was no request for syncing or collaboration.
- Set page-specific metadata for `/`, use the existing design tokens, and update `AGENTS.md` with the chosen editor integration boundary.

## Verification
- Confirm `/` loads with the drawing area and left-side controls, and verify a real freehand stroke, a standard shape, undo/redo, save/reopen, export, and presentation toggle.
- Check the board at desktop and mobile sizes so controls stay compact and usable without obstructing the writing area.
