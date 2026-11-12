PiLab Studio v5.5 — Resizable Python Editor
=========================================

WHAT'S NEW
- Drag the left edge of the Python workspace to make the editor wider or narrower on desktop.
- Drag the horizontal divider between the code editor and terminal to give more vertical space to either panel.
- Click "⛶ Expand" beside main.py for a near full-screen code editor; click "Restore" or press Esc to return.
- Panel dimensions are saved locally in the browser and restored on the next visit.
- Width and height handles also support keyboard arrow keys for accessibility (focus with Tab; use arrows; Home resets).
- The terminal's separate Expand/Shrink control continues to work.

PREVIOUS FEATURES INCLUDED
Raspberry Pi 4 40-pin GPIO header; draggable electrical components and click wiring; LED colors; button press cycles; GPIO callbacks; Python global variables; input() prompts; terminal font zoom; Python autocomplete, smart indentation, error markers; project saving and loading; stop/reset controls.

HOW TO RUN
1. Open Raspberry_Pi_4_GPIO_Lab_v5_5_RESIZABLE_EDITOR.html in a modern desktop browser.
2. Internet access is required to load the Pyodide Python interpreter.
3. If using a narrow window or zoomed display, use Expand for the largest Python editing area.
4. For standalone use, keep the HTML file. No build/install step is required.

NOTES
This is an educational GPIO simulation, not a full Raspberry Pi OS emulator.
The resizable editor was verified in a headless Chromium interface test; execution of the remote Python runtime could not be fully verified in this testing environment.
CodeMirror is distributed under the bundled MIT license.
