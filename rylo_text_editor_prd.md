# Rylo Text Editor - Product Requirements Document (PRD)

## Overview
The Rylo Text Editor is a minimalist, terminal-inspired text editor built with performance, usability, and developer ergonomics in mind. It is designed to look and feel like a retro console or emulator but packed with modern keyboard-centric functionality. It’s aimed at power users, writers, developers, and anyone who prefers keyboard-based workflows. While it offers full mouse compatibility, its core philosophy is that the entire application should be fully usable without ever touching the mouse.

---

## Product Goals
- Deliver a fully functional text editor that mimics a terminal/console emulator.
- Support text document editing with a minimal, responsive UI.
- Enable command-driven workflows through a persistent command input field.
- Ensure all major actions are controllable via keyboard shortcuts.
- Provide light plugin or customization support (themes, keybindings, config).
- Build a strong foundation for future extensibility (e.g., plugin system, scripting, VCS integration).

---

## Target Users
- Developers who prefer terminal-based or keyboard-centric workflows.
- Writers and bloggers looking for a distraction-free writing environment.
- Power users who value speed and control.
- Users of tiling window managers, Linux distros, and minimal UI environments.

---

## Features

### 1. UI & Aesthetic
- Terminal-like UI with a retro-inspired look (optional scanlines, green/amber themes).
- Monospaced font by default.
- Simple layout with two primary components:
  - **Main Text Area**: Where editing happens.
  - **Command Line Interface (CLI)**: Where users can type and run commands.
- Optional dark and light themes.

### 2. File Management
- Open files by command (e.g., `open notes.txt`).
- Create new files with command (e.g., `new blog.md`).
- Save current file (`save`) or to a new name (`saveas newname.txt`).
- Auto-backup with timestamped files (toggleable).

### 3. Multi-document Support
- Ability to open and switch between multiple documents using commands.
- Commands:
  - `switch notes.txt`
  - `close notes.txt`
- `Ctrl+Tab` and `Ctrl+Shift+Tab` for cycling through open files.

### 4. Keyboard Navigation & Shortcuts
- Fully functional without mouse.
- Essential shortcuts:
  - `Ctrl+S`: Save file
  - `Ctrl+N`: New file
  - `Ctrl+W`: Close file
  - `Ctrl+Q`: Quit application
  - `Ctrl+Tab`: Switch next file
  - `Ctrl+Shift+Tab`: Switch previous file

### 5. Command Parsing
- Central command parser for interpreting CLI input.
- Command history accessible with up/down arrows.
- Partial matching or autocomplete (e.g., `swit notes` → `switch notes.txt`).
- Help system accessible via `help`, `help open`, etc.

### 6. Appearance Customization
- Themes are configurable via external `.json` files:
  - Colors (background, foreground, cursor, selection)
  - Font size, type
  - Line spacing
- Command: `theme dark.json`

### 7. File Tree View
- Toggleable via command (`tree`).
- Displays current working directory structure.
- Mouse-compatible for navigation.

### 8. Focus Mode
- Command: `focus`
- Hides command input and all UI chrome, showing only the text editor.
- Toggleable via repeated command or `Esc` key.

### 9. Syntax Highlighting
- Minimal highlighting for `.js`, `.json`, `.md`, `.txt`, and `.py` files.
- Highlighting respects theme colors.
- Syntax toggles via command: `highlight on|off`

### 10. Configuration File
- `config.json` in app directory supports:
  - Default theme
  - Keybindings
  - Auto-backup toggle
  - Default directory path

### 11. Persistent State
- Last open files restored on relaunch.
- Command history stored between sessions.
- Theme and configuration auto-loaded on start.

---

## Technical Requirements

### Platform & Stack
- **Framework**: Electron (Node.js + Chromium)
- **UI**: HTML/CSS/JS with pre-bundled assets
- **Text Rendering**: HTML `textarea` or CodeMirror/Monaco for advanced features
- **File Handling**: Node.js `fs` module
- **Settings/Config**: JSON files stored locally

### Structure
- **Main Process**: Handles file system access, app lifecycle, config loading.
- **Renderer Process**: UI rendering, user interaction, editor view.
- **IPC Communication**: For bridging main and renderer tasks.
- **Modular Design**: Components (CommandBar, TextView, ThemeManager, etc.) in separate files.

### Performance Goals
- App launch time under 2 seconds.
- Memory usage under 200MB idle.
- File open/save under 100ms for small files (<1MB).

---

## Milestones & Timeline

### Phase 1 – MVP (2 Weeks)
- Basic UI shell (terminal aesthetic)
- Text editing area
- Command input and parser
- Open/Save/New command functionality
- Basic keyboard shortcuts

### Phase 2 – Core Features (2-3 Weeks)
- Multi-document support
- Command history
- Theme loading
- Config file support
- Syntax highlighting (basic)

### Phase 3 – Polish & Usability (2 Weeks)
- File tree toggle
- Focus mode
- Help system
- Persistent command history
- Autocomplete

---

## Risks
- Balancing retro visuals with modern readability.
- Parser errors from malformed commands.
- High memory consumption from Electron.
- Ensuring keyboard-only flow doesn’t compromise accessibility.

---

## Future Features (Post-v1)
- Plugin system for commands/extensions.
- Git integration (`git status`, `git diff` inside editor).
- Markdown preview panel.
- Live collaboration / file sharing.
- Portable/USB version.

---

## Success Metrics
- Editor is fully usable without the mouse.
- Command input system works reliably.
- App launches quickly and runs light.
- Users can theme and customize easily.
- No crashes or lost data from file operations.

---

## Conclusion
The Rylo Text Editor is designed for users who appreciate precision, speed, and keyboard control. It’s a fresh take on what a text editor can be when fused with a terminal UI and modern tooling. With an extensible foundation and strong keyboard-first philosophy, it is meant to be fast, fun, and deeply customizable while keeping system resource usage minimal.

