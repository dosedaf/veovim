# Distraction-Free Neovim: A VS Code Profile

This Visual Studio Code profile is meticulously crafted for a keyboard-centric, minimalist workflow that leverages the full power of Neovim's modal editing. It strips away UI clutter and provides fast, intuitive keybindings, allowing for deep focus on the code.

It's designed for a polyglot developer with strong support for **Go**, **Python**, **C++**, and **Java**, but is flexible enough for any language.

## Core Philosophy

* **Keyboard is King:** Every common action is mapped to an intuitive keybinding, accessible without touching the mouse.
* **Modal Editing First:** The setup is built around the `asvetliakov.vscode-neovim` extension. The keybindings and editor behavior assume you live in Normal, Insert, and Visual modes.
* **Minimalist & Distraction-Free UI:** The status bar, activity bar, and minimap are hidden by default to maximize screen real estate and focus. The sidebar is moved to the right to prevent layout shifts when opened.
* **Powerful Tooling Under the Hood:** While the UI is minimal, the profile is packed with powerful extensions for linting (`golangci-lint`), language support (`gopls`, `Pylance`), debugging, API testing, and Git integration (`GitLens`).

## Key Features

-   **Dual Leader Key System:**
    -   **`<Space>` Leader (Normal Mode):** The primary leader key for all editor and workbench actions while in Neovim's Normal Mode.
    -   **`Ctrl+Alt` Leader (Global):** A universal leader key that works in any mode or context, providing consistent access to core functions.
-   **Curated for Go Development:** Includes settings for `gopls`, auto-linting, and testing on save.
-   **Aesthetic & Readable:** Uses the "Ayu Dark" theme with the "JetBrains Mono" font and ligatures enabled for a clean, modern look.
-   **Integrated API & Data Tools:** Comes with REST Client for API testing and Rainbow CSV for data files.
-   **Rich Language Support:** Pre-configured for Go, Python, Java, C++, and Docker, with powerful language servers and debuggers.

---

## Installation & Setup

### Prerequisites

You **must** have [Neovim](https://neovim.io/) (v0.5.0 or newer) installed and available in your system's PATH. This extension embeds a real Neovim instance.

### Method 1: Import from Profile File (Recommended)

1.  Export this profile from your source machine: `Gear Icon > Profiles > Export Profile...`.
2.  Save the `.code-profile` file.
3.  On the new machine, go to `Gear Icon > Profiles > Import Profile...` and select the saved file.

### Method 2: Manual Setup

If you prefer a manual setup or want to integrate this into your dotfiles:

**1. Install the Extensions:**

Run the following command in your terminal to install all the required extensions.

```bash
#!/bin/bash
# A list of extensions from the profile
EXTENSIONS=(
  "asvetliakov.vscode-neovim"
  "bartoszmaka95.onedark"
  "eamodio.gitlens"
  "formulahendry.code-runner"
  "golang.go"
  "humao.rest-client"
  "icrawl.discord-vscode"
  "kevinrose.vsc-python-indent"
  "leonardssh.vscord"
  "mechatroner.rainbow-csv"
  "ms-azuretools.vscode-containers"
  "ms-azuretools.vscode-docker"
  "ms-python.debugpy"
  "ms-python.python"
  "ms-python.vscode-pylance"
  "ms-toolsai.jupyter"
  "ms-toolsai.jupyter-keymap"
  "ms-toolsai.jupyter-renderers"
  "ms-toolsai.vscode-jupyter-cell-tags"
  "ms-toolsai.vscode-jupyter-slideshow"
  "ms-vscode.cmake-tools"
  "ms-vscode.cpptools"
  "ms-vscode.cpptools-extension-pack"
  "ms-vscode.cpptools-themes"
  "ms-vscode.vscode-typescript-next"
  "redhat.java"
  "teabyii.ayu"
  "tomrijndorp.find-it-faster"
  "usernamehw.errorlens"
  "visualstudioexptteam.intellicode-api-usage-examples"
  "visualstudioexptteam.vscodeintellicode"
  "vscjava.vscode-gradle"
  "vscjava.vscode-java-debug"
  "vscjava.vscode-java-dependency"
  "vscjava.vscode-java-pack"
  "vscjava.vscode-java-test"
  "vscjava.vscode-maven"
  "wakatime.vscode-wakatime"
)

for extension in ${EXTENSIONS[@]}; do
  code --install-extension $extension
done
```

**2. Configure `settings.json`:**

Copy the contents of your `settings.json` file into `Preferences: Open User Settings (JSON)`.

**3. Configure `keybindings.json`:**

Copy the contents of your `keybindings.json` file into `Preferences: Open Keyboard Shortcuts (JSON)`.

---

## Keybinding Cheatsheet

### `<Space>` Leader (Neovim Normal Mode)

| Key         | Command                                | Description                      |
| :---------- | :------------------------------------- | :------------------------------- |
| `Space` `f` | `workbench.view.explorer`              | Toggle File Explorer             |
| `Space` `p` | `workbench.action.showCommands`        | Show Command Palette             |
| `Space` `o` | `workbench.action.quickOpen`           | Quick Open File (Go to File)     |
| `Space` `b` | `workbench.action.showAllEditors`      | Show All Open Editors (Buffers)  |
| `Space` `/` | `workbench.action.findInFiles`         | Find in Files (Project-wide)     |
| `Space` `t` | `workbench.action.terminal.focus`      | Focus Integrated Terminal        |
| `Space` `v` | `workbench.action.toggleSidebarVisibility` | Toggle Sidebar Visibility        |
| `Space` `g` | `workbench.view.scm`                   | Show Source Control (Git) Panel  |
| `Space` `s` | `workbench.action.files.save`          | Save Current File                |
| `Space` `w` | `workbench.action.closeActiveEditor`   | Close Active Editor (Window)     |

#### LSP & Diagnostics (`<Space>` Leader)

| Key         | Command                            | Description                     |
| :---------- | :--------------------------------- | :------------------------------ |
| `Space` `d` | `editor.action.goToDeclaration`    | Go to Declaration/Definition    |
| `Space` `i` | `editor.action.goToImplementation` | Go to Implementation            |
| `Space` `r` | `editor.action.rename`             | Rename Symbol                   |
| `Space` `a` | `editor.action.quickFix`           | Show Quick Fixes (Code Actions) |
| `Space` `h` | `editor.action.showHover`          | Show Hover Information          |
| `Space` `l` | `workbench.actions.view.problems`  | Show Problems Panel             |

### `Ctrl+Alt` Leader (Global)

These shortcuts work from anywhere in VS Code, regardless of mode.

| Key              | Command                                | Description                   |
| :--------------- | :------------------------------------- | :---------------------------- |
| `Ctrl+Alt` `f`   | `workbench.view.explorer`              | Toggle File Explorer          |
| `Ctrl+Alt` `p`   | `workbench.action.showCommands`        | Show Command Palette          |
| `Ctrl+Alt` `o`   | `workbench.action.quickOpen`           | Quick Open File (Go to File)  |
| `Ctrl+Alt` `t`   | `workbench.action.terminal.focus`      | Focus Integrated Terminal     |
| `Ctrl+Alt` `v`   | `workbench.action.toggleSidebarVisibility` | Toggle Sidebar Visibility     |
| `Ctrl+Alt` `s`   | `workbench.action.files.save`          | Save Current File             |
| `Ctrl+Alt` `w`   | `workbench.action.closeActiveEditor`   | Close Active Editor (Window)  |

## Credit
Yes, this readme is AI generated. shoutout to Gemini fr
