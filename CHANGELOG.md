# Changelog

All notable changes to this project will be documented in this file.

## [v1.0.0] - 2025-10-25

Initial release of ConsoleApp.

### ✨ Added

* **(Core) Console Interception:**
    * Automatically intercepts and redirects all `Console.WriteLine()` output to the console window.
    * Automatically intercepts all `Console.Error.WriteLine()` streams (which typically include unhandled `Exception` output).

* **(UI) Dockable Pane Interface:**
    * Provides a modern WPF Dockable Pane that can be docked anywhere in the Revit UI.
    * The console interface is `IsReadOnly` (read-only) and uses the `Consolas` font for log readability.

* **(UX) Theme Support (Light/Dark):**
    * Adds a context menu item to toggle between Light and Dark themes.
    * The user's theme preference is automatically saved to their `user.config` file (using `Properties.Settings.Default`) and reloaded on startup.

* **(UX) Auto-Shortcut Assignment:**
    * On startup, the add-in checks the user's `KeyboardShortcuts.xml` file.
    * If the "Show Console" command does not have a shortcut, the add-in automatically creates and assigns the `CW` shortcut.
    * If a shortcut is already assigned by the user, the add-in does nothing, respecting the user's settings.

* **(UI) Context Menu:**
    * Implements a full-featured context menu directly on the `TextBox`:
        * **Clear** (Hotkey: `F5`): Clears all content from the console.
        * **Copy** (Hotkey: `Ctrl+C`): Copies the selected text.
        * **Select All** (Hotkey: `Ctrl+A`): Selects all text.
        * **Change Theme**: Toggles between Light and Dark themes.

* **(UI) Ribbon Button:**
    * Adds a "Console" button to the "Add-Ins" tab with a custom icon.
    * The button includes a clear Tooltip (`Show/Close Console Dock`) and Long Description.

* **(Performance) Buffering Mechanism:**
    * Uses a `DispatcherTimer` and a buffer (`ConsoleBufferLines`) to batch UI updates.
    * This prevents Revit from crashing or lagging when a massive number of logs (e.g., 10,000 lines in a `for` loop) are written to the console simultaneously.

* **(Deployment) Inno Setup Installer:**
    * Creates a professional `.exe` installer.
    * Automatically installs to the correct `%APPDATA%\...` folder (using `PrivilegesRequired=lowest` to avoid unnecessary Admin prompts).
    * Automatically (and silently) uninstalls any previous version before installing the new one.
    * Provides a clean uninstaller that completely removes the bundle directory on removal.

* **(Docs) Documentation:**
    * Added a detailed `README.md` explaining features, `.exe` installation, and uninstallation.
    * Added a `PRIVACY.md` policy, clarifying that the add-in only stores local theme/shortcut settings and collects no personal or model data.
