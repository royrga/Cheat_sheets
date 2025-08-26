---
tags:
  - Tools
---
# VIM (Vi IMproved)

VIM is a highly configurable, modal text editor built to enable efficient text editing. It is an enhanced version of the classic `vi` editor, ubiquitous on Unix systems. Its core philosophy is that a programmer's hands should stay on the home row of the keyboard, minimizing the need for mouse usage and arrow keys, which dramatically increases editing speed once mastered.

**Key Characteristics:**
*   **Modal Editing:** Its most distinctive feature. Different modes interpret keystrokes differently.
    *   **Normal Mode:** For navigation and manipulation of text (default mode on startup).
    *   **Insert Mode:** For typing text directly.
    *   **Visual Mode:** For selecting text blocks.
    *   **Command-Line Mode:** For entering commands to save, quit, search, etc.

---

## VIM Cheatsheet

### Mode Navigation
| Command | Description |
| :--- | :--- |
| `i` | Enter **Insert** mode at the cursor. |
| `a` | Enter **Insert** mode *after* the cursor (Append). |
| `I` | Enter **Insert** mode at the beginning of the line. |
| `A` | Enter **Insert** mode at the end of the line. |
| `v` | Enter **Visual** mode (character-wise). |
| `V` | Enter **Visual Line** mode (line-wise). |
| `Ctrl-v` | Enter **Visual Block** mode (block-wise). |
| `Esc` or `Ctrl-[` | Return to **Normal** mode from any other mode. |
| `:` | Enter **Command-Line** mode. |

### Saving and Exiting (Command-Line Mode)
| Command               | Description                                    |
| :-------------------- | :--------------------------------------------- |
| `:w`                  | **W**rite (save) the file.                     |
| `:q`                  | **Q**uit (fails if there are unsaved changes). |
| `:q!`                 | Quit **discarding** any unsaved changes.       |
| `:wq` or `:x` or `ZZ` | Write the file and quit.                       |
| `:w [filename]`       | Write to `[filename]` (save as).               |

### Basic Movement (Normal Mode)
| Command         | Description                                        |
| :-------------- | :------------------------------------------------- |
| `h` `j` `k` `l` | Move left, down, up, right.                        |
| `w`             | Move forward to the start of the next **word**.    |
| `b`             | Move **back** to the start of the previous word.   |
| `0` (zero)      | Move to the **beginning** of the line.             |
| `$`             | Move to the **end** of the line.                   |
| `gg`            | Go to the **first** line of the file.              |
| `G`             | Go to the **last** line of the file.               |
| `[number]G`     | Go to line `[number]` (e.g., `5G` goes to line 5). |
| `Ctrl-u`        | Move **Up** half a page.                           |
| `Ctrl-d`        | Move **Down** half a page.                         |

### Editing (Normal Mode)
Commands can be prefixed with a number (e.g., `4dw` deletes 4 words).

| Command  | Description                                        |
| :------- | :------------------------------------------------- |
| `x`      | Delete character under the cursor (like *cut*).    |
| `dw`     | **D**elete from cursor to end of **word**.         |
| `dd`     | **D**elete the entire current line (cut).          |
| `D`      | Delete from cursor to end of line.                 |
| `yw`     | **Y**ank (copy) from cursor to end of word.        |
| `yy`     | **Y**ank (copy) the entire current line.           |
| `p`      | **P**aste after the cursor.                        |
| `P`      | **P**aste before the cursor.                       |
| `u`      | **U**ndo the last action.                          |
| `Ctrl-r` | **R**edo (reverse undo).                           |
| `r`      | **R**eplace the single character under the cursor. |
| `J`      | Join the current line with the line below.         |

### Searching and Replacing
| Command          | Description                                               |
| :--------------- | :-------------------------------------------------------- |
| `/pattern`       | Search **forward** for `pattern`.                         |
| `?pattern`       | Search **backward** for `pattern`.                        |
| `n`              | Repeat the last search in the same direction.             |
| `N`              | Repeat the last search in the opposite direction.         |
| `:%s/old/new/g`  | **S**ubstitute `old` with `new` **g**lobally in the file. |
| `:%s/old/new/gc` | Substitute with **c**onfirmation for each match.          |

^1d142e

### Working with Multiple Files (Command-Line Mode)
| Command           | Description                                    |
| :---------------- | :--------------------------------------------- |
| `:e [filename]`   | **E**dit a different file.                     |
| `:vsp [filename]` | Open a file in a **v**ertical **sp**lit.       |
| `:sp [filename]`  | Open a file in a horizontal split (**sp**lit). |
| `Ctrl-w w`        | Switch between open windows.                   |
| `:bn`             | Go to the **n**ext buffer.                     |
| `:bp`             | Go to the **p**revious buffer.                 |
| `:bd`             | **D**elete/close the current buffer.           |

### Getting Help
| Command | Description |
| :--- | :--- |
| `:help` | Open the main help document. |
| `:help [topic]` | Get help on a specific topic (e.g., `:help w`). |

> **Pro Tip:** VIM's power comes from combining commands. For example, `d$` means "delete from the cursor to the end of the line," and `caw` means "change around word" (delete a word and enter insert mode).