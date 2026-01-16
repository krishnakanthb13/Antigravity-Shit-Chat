# Antigravity Phone Connect 📱

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

**Antigravity Phone Connect** is a high-performance, real-time mobile monitor and remote control for your Antigravity AI sessions. It allows you to step away from your desk while keeping full sight and control over your AI's thinking process and generations.

**Note:** This project is a refined fork/extension based on the original [Antigravity Shit-Chat](https://github.com/gherghett/Antigravity-Shit-Chat) by gherghett.

---

## 🚀 Quick Start

### Windows

1.  **Double-click `start_ag_phone_connect.bat`**
    The script will:
    - Verify Node.js is installed.
    - Automatically install dependencies (`npm install`) if they are missing.
    - Detect and display your **exact IP Address** (e.g., `http://192.168.1.5:3000`).
    - Provides a tip to use `install_context_menu.bat` for context menu management.

2.  **Connect Your Phone**
    - Ensure your phone is on the **same Wi-Fi network** as your PC.
    - Open your mobile browser and enter the **URL shown in the terminal**.

3.  **Launch Antigravity** (if not already running)
    - **Recommended**: Run **`install_context_menu.bat`** and select **[1] Install**. Then, simply right-click any project folder and select **"Open with Antigravity (Debug)"**.
    - Otherwise, run manually: `antigravity . --remote-debugging-port=9000`

---

### macOS / Linux

1.  **Run the launcher script**
    ```bash
    chmod +x start_ag_phone_connect.sh
    ./start_ag_phone_connect.sh
    ```
    The script will:
    - Verify Node.js is installed.
    - Automatically install dependencies.
    - Detect and display your **exact IP Address**.
    - *(Linux only)* Provides a tip to use `./install_context_menu.sh` for Nautilus/GNOME context menu management.
    - *(macOS)* Provide a command to create a fast shell alias (`ag-debug`).

2.  **Connect Your Phone**
    - Ensure your phone is on the **same Wi-Fi network**.
    - Open your mobile browser and enter the **URL shown in the terminal**.

3.  **Launch Antigravity** (if not already running)
    ```bash
    antigravity . --remote-debugging-port=9000
    ```

---

### macOS: Adding Right-Click "Quick Action" (Optional)

Since macOS requires Automator for context menu entries, follow these steps manually:

1.  Open **Automator** (Spotlight → type "Automator").
2.  Click **File → New** and select **Quick Action**.
3.  At the top, set:
    - "Workflow receives current" → **folders**
    - "in" → **Finder**
4.  In the left sidebar, search for **"Run Shell Script"** and drag it to the right pane.
5.  Set "Shell" to `/bin/zsh` and "Pass input" to **as arguments**.
6.  Paste this script:
    ```bash
    cd "$1"
    antigravity . --remote-debugging-port=9000
    ```
7.  **Save** the Quick Action with a name like `Open with Antigravity (Debug)`.
8.  Now you can right-click any folder in Finder → **Quick Actions → Open with Antigravity (Debug)**.

---

## ✨ Features
- **Real-Time Mirroring**: 1-second polling interval for a near-instant sync experience.
- **Remote Control**: Send messages, stop generations, and switch Modes (Fast/Planning) or Models (Gemini/Claude/GPT) directly from your phone.
- **Thought Expansion**: Tap on "Thinking..." or "Thought" blocks on your phone to remotely expand them in the desktop IDE.
- **Smart Sync**: Bi-directional synchronization ensures your phone always shows the current Model and Mode selected on your desktop. Press Refresh to force a full sync.
- **Premium Mobile UI**: A sleek, dark-themed interface optimized for touch interaction and long-form reading.
- **Context Menu Management**: Dedicated scripts to **Install, Remove, or Backup** your Right-Click integrations on Windows and Linux.
- **Zero-Config**: The launch scripts handle the heavy lifting of environment setup.

---

## 📂 Documentation
For more technical details, check out:
- [**Code Documentation**](CODE_DOCUMENTATION.md) - Architecture, Data Flow, and API.
- [**Design Philosophy**](DESIGN_PHILOSOPHY.md) - Why it was built this way.
- [**Contributing**](CONTRIBUTING.md) - Guidelines for developers.

---

## License
Licensed under the [GNU GPL v3](LICENSE).  
Copyright (C) 2026 **Krishna Kanth B** (@krishnakanthb13)
