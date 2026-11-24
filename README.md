# PiLab Studio v6 — Raspberry Pi OS Lab

Open `index.html` in Chrome or Edge. The terminal shell works locally; Python execution uses Pyodide loaded from the jsDelivr CDN, so internet access is required to start the Python runtime.

## Workspaces
- **Circuit & Python**: the original v5.5 GPIO simulator, smart editor, callbacks, terminal input and resize controls.
- **Pi OS Terminal**: a simulated Linux shell, two virtual computers, local file storage, simulated Python virtual environments, pip, SSH and SCP. Click Show circuit to watch the same virtual GPIO circuit while executing scripts.

## Lab practice
1. Select Raspberry Pi 4 and type `hostname -I`. The virtual Pi address is 192.168.1.10.
2. Select Ubuntu laptop. Type `ssh pi@192.168.1.10` and enter the practice password `raspberry`.
3. `mkdir my_project && cd my_project`
4. `python -m venv env`
5. `source env/bin/activate`
6. `pip3 install RPi.GPIO`
7. `nano simple_io.py` — type your Python script. Ctrl+O saves; Ctrl+X exits. Alternatively save code from the original editor into a virtual file.
8. Load the GPIO17 LED circuit or wire an LED with a 330-ohm resistor yourself. Click Show circuit, then `python3 simple_io.py`.
9. Ctrl+C requests a cooperative Python KeyboardInterrupt, allowing try/finally cleanup for yielding scripts. If the program does not yield, the app forces a worker shutdown and resets GPIO.
10. `deactivate`, then `exit` to return to Ubuntu.
11. `scp pi@192.168.1.10:/home/pi/my_project/simple_io.py .` and enter the practice password. To copy back: `scp simple_io.py pi@192.168.1.10:/home/pi/my_project`.

Type `help` for other supported commands. Files are saved in browser storage; use Download selected file for backups. Virtual files are separate from the circuit project JSON. Text files are mirrored into the browser Python filesystem for script execution; new or changed supported text files are copied back after normal/cooperative completion. A forced stop cannot guarantee file synchronization.

## Limits
This is not Raspberry Pi OS, a Bash implementation, an ARM emulator, or real SSH/SCP networking. Virtual environment and pip commands maintain simulated metadata rather than creating actual isolated interpreters or installing Linux packages. The GPIO libraries are PiLab's simulated Python modules. Not every shell command, Python package or hardware behavior is supported. The virtual password is for practice only. No real SSH credentials should be entered. Ctrl+C can run cleanup on cooperative code, while Stop deliberately forces reset. The simulator is not a substitute for hardware safety tests.

## GitHub Pages
Replace your repository's existing `index.html` with the included `index.html`. Commit the change. Keep your repository's existing license and retain the CodeMirror MIT license included here. Test the hosted site, including live Pyodide loading and GPIO operation.

## Verification
Automated browser tests used a mocked Python worker to check the shell, SSH/SCP workflows, nano, run routing, circuit split and stop controls. A separate CPython test checked module execution, cwd, arguments, input and finally cleanup. The live CDN-loaded Pyodide runtime was not verified end-to-end in the test environment.
