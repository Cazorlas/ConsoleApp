# ConsoleApp for Revit

A simple but powerful developer console for intercepting `Console.WriteLine()` output within the Autodesk Revit environment.

<img width="1920" height="1032" alt="Console" src="https://github.com/user-attachments/assets/6e2ea9ff-6f96-4081-808b-95c8b0700101" />

---

This add-in provides a dockable WPF pane inside Revit. It automatically captures all standard output (`Console.WriteLine`) and standard error (`Console.Error.WriteLine`) streams from any loaded add-in. This allows you to debug your add-ins in real-time without needing to attach a debugger or write to external log files.

## ✨ Features

* **Real-time Interception:** Automatically captures all `Console.WriteLine()` and `Console.Error.WriteLine()` streams.
* **Dockable WPF Pane:** A clean, modern UI that docks anywhere in your Revit workspace.
* **Theme Aware:** Automatically detects and switches between Revit's Light and Dark themes based on your settings.
* **Auto-Shortcut:** Automatically assigns the `CW` keyboard shortcut on first launch (if available) for quick access.
* **Built-in Context Menu:** Includes "Clear", "Copy", and "Select All" for easy log management.

## 💾 Installation

1.  Go to the [Releases](https://github.com/Cazorlas/ConsoleApp/releases/tag/v1.0.0) page.
2.  Download the latest `ConsoleApp.1.0.0.exe` installer.
3.  Run the installer (e.g., `ConsoleApp.1.0.0.exe`).
4.  Follow the on-screen instructions. The installer will automatically find the correct folder.
5.  Start Revit.

## ⛔ Uninstallation

1.  Close all instances of Revit.
2.  Go to **Add or remove programs** in Windows Settings.
3.  Find **ConsoleApp** in the app list.
4.  Click "Uninstall" and follow the prompts. The uninstaller will remove all files and folders cleanly.

## 🚀 How to Use

1.  Launch Revit.
2.  Open the console from the **Add-Ins** tab on the ribbon, or by using the `CW` keyboard shortcut.
3.  Run any add-in (yours or others).
4.  Watch the output appear instantly in the console window.
5.  In your own add-in's code, simply use `Console.WriteLine("Your debug message");` to log.

## 💻 Building from Source

This project is configured to multi-target several Revit versions.
1.  Clone this repository.
2.  Open `ConsoleApp.sln` in Visual Studio.
3.  Ensure your Revit API DLLs (`RevitAPI.dll`, `RevitAPIUI.dll`) are correctly referenced.
4.  Select your desired build configuration (e.g., `RL2025` for Release Revit 2025).
5.  Build the project. The Post-Build event will automatically copy the necessary files to your `%APPDATA%\Autodesk\ApplicationPlugins` folder for testing.
