# Ergonomic Neovim: A VS Code Profile for Compact Keyboards

This Visual Studio Code profile has been completely refactored for an ergonomic, keyboard-centric workflow, specifically tailored for **60% and other compact keyboards**. It eliminates uncomfortable key combinations in favor of a fast, logical, and comfortable leader key system.

The entire configuration is built around the **VSCode Neovim** extension, assuming a modal editing workflow where the keyboard is your primary tool.

---

## Core Philosophy

- **Ergonomics First:** Every keybinding is designed to reduce hand strain. Uncomfortable combinations like `Ctrl+Alt` have been completely replaced with simpler, more accessible patterns.
- **Leader Keys are King:** Instead of complex chords requiring multiple simultaneous key presses, this setup relies on easy-to-press leader keys (`Alt` and `<Space>`) followed by simple, mnemonic characters.
- **Logical Namespaces:** Commands are grouped into intuitive "menus" under the `<Space>` leader. Want to do something with a terminal? All commands start with `space t`. Language-specific actions? `space l`. This makes the system predictable and easy to learn.
- **Distraction-Free UI:** The profile is designed to work with a minimalist UI (hidden activity bar, status bar, etc.) to maximize focus on the code.

---

## Key Features

- **Dual Leader Key System:**
  - **`Alt` Leader (Global):** Your go-to for essential, global workbench actions like toggling UI panels. It's simple, fast, and works from anywhere in VS Code.
  - **`<Space>` Leader (Modal):** Your primary command center while in Neovim's Normal Mode. It's a powerful and organized menu for all file, project, and editor-specific actions.
- **Optimized for Compact Keyboards:** By avoiding multi-modifier chords, this setup is perfect for 60% layouts where function keys and other keys are on different layers.
- **Full Neovim Integration:** All `<Space>` keybindings are carefully configured with `when` clauses to only be active outside of Insert Mode, ensuring the spacebar works as expected when typing.

---

## Installation

### Prerequisites

You **must** have [Neovim](https://neovim.io/) (v0.5.0 or newer) installed and available in your system's PATH.

### Steps

1.  **Install Extensions:** Run the command below in your terminal to install all the necessary extensions for this profile.

    ```bash
    #!/bin/bash
    EXTENSIONS=(
      "asvetliakov.vscode-neovim"
      "eamodio.gitlens"
      "formulahendry.code-runner"
      "golang.go"
      "humao.rest-client"
      "kevinrose.vsc-python-indent"
      "mechatroner.rainbow-csv"
      "ms-azuretools.vscode-docker"
      "ms-python.python"
      "ms-python.vscode-pylance"
      "ms-toolsai.jupyter"
      "ms-vscode.cpptools"
      "redhat.java"
      "teabyii.ayu"
      "usernamehw.errorlens"
      "visualstudioexptteam.vscodeintellicode"
      "vscjava.vscode-java-pack"
      "wakatime.vscode-wakatime"
    )

    for extension in ${EXTENSIONS[@]}; do
      code --install-extension $extension
    done
    ```

2.  **Configure `keybindings.json`:** Replace the entire contents of your `keybindings.json` file (`Preferences: Open Keyboard Shortcuts (JSON)`) with the new configuration.

3.  **Configure `settings.json`:** Ensure your `settings.json` reflects your minimalist UI preferences (hiding activity bar, etc.).

---

## Keybinding Cheatsheet

### Global Leader Key: `Alt`

These are your instant-access global commands that work from anywhere.

| Key     | Command                                        | Description                  |
| :------ | :--------------------------------------------- | :--------------------------- |
| `alt+f` | `workbench.view.explorer`                      | Toggle File Explorer         |
| `alt+o` | `workbench.action.quickOpen`                   | Quick Open File (Go to File) |
| `alt+t` | `workbench.action.terminal.focus`              | Focus Terminal               |
| `alt+p` | `workbench.action.showCommands`                | Show Command Palette         |
| `alt+g` | `workbench.view.scm`                           | Show Git/SCM Panel           |
| `alt+v` | `workbench.action.toggleSidebarVisibility`     | Toggle Sidebar Visibility    |
| `alt+a` | `workbench.action.toggleActivityBarVisibility` | Toggle Activity Bar          |
| `alt+m` | `workbench.action.toggleMenuBar`               | Toggle Menu Bar              |

### Primary Leader Key: `<Space>` (Normal Mode Only)

This is your main command menu from within Neovim's Normal Mode.

#### File & Buffer (`<Space> f`, `<Space> b`)

| Key         | Command                              | Description                 |
| :---------- | :----------------------------------- | :-------------------------- |
| `space f s` | `workbench.action.files.save`        | **F**ile **S**ave           |
| `space f w` | `workbench.action.closeActiveEditor` | **F**ile **W**indow (Close) |
| `space b b` | `workbench.action.showAllEditors`    | Show All **B**uffers        |
| `space b ]` | `workbench.action.nextEditor`        | Next **B**uffer             |
| `space b [` | `workbench.action.previousEditor`    | Previous **B**uffer         |

#### Terminal (`<Space> t`)

| Key         | Command                                   | Description              |
| :---------- | :---------------------------------------- | :----------------------- |
| `space t t` | `workbench.action.terminal.focus`         | Focus **T**erminal       |
| `space t n` | `workbench.action.terminal.new`           | **N**ew Terminal         |
| `space t d` | `workbench.action.terminal.kill`          | **D**elete/Kill Terminal |
| `space t ]` | `workbench.action.terminal.focusNext`     | Next Terminal            |
| `space t [` | `workbench.action.terminal.focusPrevious` | Previous Terminal        |
| `space t 1` | `workbench.action.terminal.focusAtIndex1` | Focus Terminal 1         |

#### Language & Diagnostics (`<Space> l`)

| Key         | Command                            | Description                  |
| :---------- | :--------------------------------- | :--------------------------- |
| `space l d` | `editor.action.goToDeclaration`    | **D**eclaration              |
| `space l i` | `editor.action.goToImplementation` | **I**mplementation           |
| `space l r` | `editor.action.rename`             | **R**ename                   |
| `space l a` | `editor.action.quickFix`           | Code **A**ctions (Quick Fix) |
| `space l h` | `editor.action.showHover`          | **H**over Info               |
| `space l p` | `workbench.actions.view.problems`  | Show **P**roblems Panel      |

#### Search (`<Space> s`), Project (`<Space> p`), and Git (`<Space> g`)

| Key         | Command                         | Description                    |
| :---------- | :------------------------------ | :----------------------------- |
| `space s f` | `workbench.action.findInFiles`  | **S**earch **F**iles (Project) |
| `space s s` | `workbench.action.gotoSymbol`   | **S**earch **S**ymbol in File  |
| `space p p` | `workbench.action.showCommands` | Show Command **P**alette       |
| `space g g` | `workbench.view.scm`            | Show **G**it/SCM Panel         |
