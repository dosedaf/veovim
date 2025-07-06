# Veovim: VS Code Keybindings for Neovim Users

This document outlines a highly ergonomic and philosophically consistent set of keybindings for Visual Studio Code, designed specifically for users who rely heavily on the [VSCode Neovim](https://marketplace.visualstudio.com/items?itemName=vscode-neovim.neovim) extension.

The goal is to blend the modal efficiency of Neovim with the powerful UI and features of VS Code, creating a seamless and intuitive workflow that minimizes finger strain and cognitive load.

_Last Updated: July 6, 2025_

---

## The Core Philosophy

This configuration is built on a simple but powerful principle: **separate your in-editor actions from your UI management actions.**

### 1. `<Space>` is your In-Editor "Leader" Key

The `Space` key acts as the leader for all commands that **keep your focus within the editor**. These are actions related to your code workflow: finding files, navigating symbols, cycling through buffers, and using LSP features. Using `<Space>` keeps these common actions fast, ergonomic, and close to the home row, extending Neovim's grammar without leaving the editing context.

### 2. `Alt` is your UI Management Key

The `Alt` key is used for all commands that **manage the VS Code user interface or change focus to a different panel**. This includes opening the explorer, focusing the terminal, toggling the sidebar, or hiding panels. This creates a clear mental model: `Alt` manipulates the "chrome" of the application, while `<Space>` manipulates the code within it.

---

## Installation

1.  Open the Command Palette: `Ctrl+Shift+P` (or `Cmd+Shift+P` on macOS).
2.  Search for and select **"Preferences: Open Keyboard Shortcuts (JSON)"**.
3.  Copy the entire `keybindings.json` configuration we've built and paste it into this file.
4.  Save the file. The keybindings will be active immediately.

---

## Keybinding Cheatsheet

### In-Editor Workflows (`<Space>` Leader Key)

_Actions that keep you in the flow of editing code._

| Keybinding        | Description                                           | VS Code Command                    |
| :---------------- | :---------------------------------------------------- | :--------------------------------- |
| `<Space>` `y`     | Yank selection to system clipboard _(in Visual Mode)_ | `vscode-neovim.send`               |
| `<Space>` `f`     | Fuzzy-find a file (Quick Open)                        | `workbench.action.quickOpen`       |
| `<Space>` `/`     | Find in all files (project-wide search)               | `workbench.action.findInFiles`     |
| `<Space>` `s`     | Go to symbol in the current file                      | `workbench.action.gotoSymbol`      |
| `<Space>` `g` `d` | Go to definition                                      | `editor.action.revealDefinition`   |
| `<Space>` `g` `i` | Go to implementation                                  | `editor.action.goToImplementation` |
| `<Space>` `l`     | Cycle to the next editor/buffer                       | `workbench.action.nextEditor`      |
| `<Space>` `h`     | Cycle to the previous editor/buffer                   | `workbench.action.previousEditor`  |

### Panel & UI Management (`Alt` Modifier)

_Actions for managing the VS Code interface and changing focus._

| Keybinding        | Description                               | VS Code Command                            |
| :---------------- | :---------------------------------------- | :----------------------------------------- |
| `Alt` `j`         | **Focus on the editor group**             | `workbench.action.focusActiveEditorGroup`  |
| `Alt` `k`         | **Toggle visibility of the bottom panel** | `workbench.action.togglePanel`             |
| `Alt` `b`         | Toggle visibility of the sidebar          | `workbench.action.toggleSidebarVisibility` |
| `Alt` `m`         | Toggle visibility of the menu bar         | `workbench.action.toggleMenuBar`           |
| `Alt` `e`         | Toggle visibility of the file explorer    | `workbench.view.explorer`                  |
| `Alt` `t`         | Focus on the terminal panel               | `workbench.action.terminal.focus`          |
| `Alt` `Shift` `t` | Create a new terminal                     | `workbench.action.terminal.new`            |
| `Alt` `x`         | Open the extensions view                  | `workbench.view.extensions`                |
| `Alt` `p`         | Toggle visibility of the problems panel   | `workbench.actions.view.problems`          |

### Contextual: Terminal Management

_Shortcuts that work **only when the terminal is focused**._

| Keybinding | Description                              | VS Code Command                           |
| :--------- | :--------------------------------------- | :---------------------------------------- |
| `Alt` `s`  | Split the active terminal                | `workbench.action.terminal.split`         |
| `Alt` `w`  | Cycle focus between split terminal panes | `workbench.action.terminal.focusNextPane` |
| `Alt` `q`  | Kill the focused terminal                | `workbench.action.terminal.kill`          |
| `Alt` `l`  | Cycle to the next terminal tab           | `workbench.action.terminal.focusNext`     |
| `Alt` `h`  | Cycle to the previous terminal tab       | `workbench.action.terminal.focusPrevious` |

### Contextual: Explorer Management

_Shortcuts that work **only when the file explorer is focused**._

| Keybinding  | Description                        | VS Code Command      |
| :---------- | :--------------------------------- | :------------------- |
| `a`         | Create a new file                  | `explorer.newFile`   |
| `Shift` `a` | Create a new directory             | `explorer.newFolder` |
| `d`         | Delete the selected file/directory | `deleteFile`         |
| `r`         | Rename the selected file/directory | `renameFile`         |

---

## A Note on Customization

This keybinding set is designed to be a powerful and ergonomic starting point. Feel free to treat it as a template. You can easily edit the `keybindings.json` file to change, add, or remove shortcuts to perfectly match your personal workflow.

Happy grinding!
