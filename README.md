# Rylo Text Editor

A minimalist, terminal-inspired text editor built with Electron. Designed for keyboard-centric workflows with retro console aesthetics and modern functionality.

![Rylo Text Editor](https://img.shields.io/badge/version-1.0.0-green) ![Electron](https://img.shields.io/badge/electron-37.2.6-blue) ![License](https://img.shields.io/badge/license-MIT-blue)

## ✨ Features

### 🎯 Core Functionality
- **Terminal-inspired UI** with retro aesthetics and multiple themes
- **Command-driven workflow** with persistent command line interface
- **Full keyboard navigation** - designed to work entirely without mouse
- **Real-time cursor position tracking** (line:column display)
- **Resizable command panel** for optimal workspace customization
- **Focus mode** for distraction-free writing

### 📁 File Management
- Create new files with `new` command
- Open files with `open [filename]` command or file dialog
- Save with `save` command or Ctrl+S
- Save As with `saveas <filename>` command
- Automatic unsaved changes detection
- Support for multiple file types (.txt, .md, .js, .json, .py, .html, .css)

### 🎨 Themes & Customization
- **4 Built-in Themes:**
  - **Black & White** - Clean monochrome theme (default)
  - **Default Terminal** - Classic green terminal
  - **Amber Terminal** - Retro amber CRT style
  - **Light Mode** - Light theme for daytime use
- Switch themes with `theme <theme-name>` command
- Themes persist between sessions
- Easy theme dropdown in status bar

### ⌨️ Keyboard Shortcuts
- `Ctrl+N` - New file
- `Ctrl+O` - Open file dialog
- `Ctrl+S` - Save file
- `Ctrl+Shift+S` - Save As
- `Ctrl+Q` - Quit application
- `Escape` - Switch between editor and command input
- `Tab` - Insert 4 spaces (proper indentation)
- `F11` - Toggle focus mode

### 🖥️ Command System
- **File Commands:**
  - `new` - Create new file
  - `open [filename]` - Open file (shows dialog if no filename)
  - `save` - Save current file
  - `saveas <filename>` - Save with new name

- **Application Commands:**
  - `help` - Show all available commands
  - `clear` - Clear command output
  - `exit` / `quit` - Exit application (prompts to save)
  - `focus` - Toggle focus mode
  - `stats` - Show document statistics

- **Theme Commands:**
  - `theme <name>` - Switch to theme
  - `themes` - List available themes

- **Command Features:**
  - Command history with ↑/↓ arrow keys
  - Tab completion for commands
  - Persistent command history between sessions

## 🚀 Installation & Usage

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn

### Quick Start

1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd rylo-text-editor
   ```

2. **Navigate to the application directory:**
   ```bash
   cd "rylo text editor"
   ```

3. **Install dependencies:**
   ```bash
   npm install
   ```

4. **Run the application:**
   ```bash
   npm start
   ```

### Development Mode
```bash
npm run dev
```
This opens the application with developer tools enabled.

### Building for Distribution
```bash
# Build for current platform
npm run build

# Build for specific platforms
npm run build-win    # Windows
npm run build-mac    # macOS
npm run build-linux  # Linux
```

## 🎮 How to Use

### Getting Started
1. Launch the application
2. Start typing in the main text area
3. Use the command input at the bottom for file operations
4. Type `help` to see all available commands

### Basic Workflow
1. **Create a new file:** Type `new` in command input
2. **Open existing file:** Type `open filename.txt` or just `open` for dialog
3. **Save your work:** Press `Ctrl+S` or type `save`
4. **Switch themes:** Type `theme amber` or use the dropdown
5. **Focus mode:** Press `F11` or type `focus` for distraction-free writing

### Tips
- Use `Escape` to quickly switch between editor and command input
- Command history is accessible with ↑/↓ arrows
- Tab completion works for commands
- The status bar shows current file and cursor position
- Resize the command panel by dragging the top border

