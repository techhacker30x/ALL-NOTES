# Vim Commands Cheat Sheet

A beginner‑friendly Vim reference for daily development work. This README is structured for quick lookup and GitHub readability.

---

## Table of Contents
- [Insert Modes](#insert-modes)
- [Saving & Quitting](#saving--quitting)
- [Cursor Movement](#cursor-movement)
- [Indentation](#indentation)
- [Searching](#searching)
- [Search & Replace](#search--replace)
- [Navigation](#navigation)
- [Undo & Redo](#undo--redo)
- [Deletion](#deletion)
- [Change Commands](#change-commands)
- [Visual Modes](#visual-modes)
- [Copy & Paste](#copy--paste)
- [Replace](#replace)
- [Marks & Jumps](#marks--jumps)
- [Macros](#macros)
- [Vim Configuration](#vim-configuration)

---

## Insert Modes

Insert mode allows you to start typing text into the file.

| Command | Description | Example |
|-------|-------------|---------|
| `i` | Insert before cursor | Cursor on `H`, `iHello` → `HelloH` |
| `I` | Insert at start of line | `I#include<stdio.h>` |
| `a` | Append after cursor | Cursor on `H`, `aello` → `Hello` |
| `A` | Append at end of line | `A;` adds semicolon at end |
| `o` | New line below | Creates line below and enters insert |
| `O` | New line above | Creates line above and enters insert |

-------|-------------|
| `i` | Insert before cursor |
| `I` | Insert at start of line |
| `a` | Append after cursor |
| `A` | Append at end of line |
| `o` | New line below |
| `O` | New line above |

---

## Saving & Quitting

Commands used to save, quit, and manage Vim sessions.

| Command | Description | Example |
|--------|-------------|---------|
| `:w` | Write (save) file | Save changes |
| `:q` | Quit file | Quit if no changes |
| `:q!` | Quit without saving | Discard changes |
| `:x` | Save and quit | Same as `:wq` |
| `:wq` | Write and quit | Combined command |
| `:reg` | View clipboard/registers | Shows yank history |
| `"5p` | Paste from register 5 | Paste specific buffer |

**Notes:**
- You can prefix commands with numbers (e.g., `5dd`, `3u`).
- Lowercase commands usually move **forward**.
- Uppercase commands usually move **backward**.

**Special Commands:**
- `zz` → Center current line on screen
- `.` → Repeat last command (e.g., `dd.` deletes next line)

-------|-------------|
| `:w` | Save file |
| `:q` | Quit |
| `:q!` | Quit without saving |
| `:x` / `:wq` | Save and quit |
| `:reg` | View clipboard registers |
| `"5p` | Paste register 5 |

Notes:
- Commands can be prefixed with numbers.
- Lowercase moves forward, uppercase moves backward.

---

## Cursor Movement

Efficient navigation is the core strength of Vim.

| Command | Action | Example |
|-------|--------|---------|
| `h j k l` | Left, Down, Up, Right | `5j` → move 5 lines down |
| `w` | Next word (any separator) | `this-is-test` → jumps across `-` |
| `W` | Next word (space only) | Stops only at spaces |
| `b / B` | Previous word | Jump backward |
| `e / E` | End of word | Move to last char |
| `0` | Start of line | Cursor to column 0 |
| `$` | End of line | Cursor to last char |
| `%` | Matching brackets | `{}` `()` `[]` |
| `t,` | Jump before `,` | Useful in arguments |
| `f,` | Jump onto `,` | Exact match |

-------|--------|
| `h j k l` | Left, Down, Up, Right |
| `w / W` | Next word (symbol / space) |
| `b / B` | Previous word |
| `e / E` | End of word |
| `0` | Start of line |
| `$` | End of line |
| `%` | Matching brackets |
| `gg` | Start of file |
| `G` | End of file |

---

## Indentation

Used to align code blocks correctly.

| Command | Description | Example |
|--------|-------------|---------|
| `==` | Auto-indent current line | Useful in C blocks |
| `V` + `==` | Indent selected lines | Visual line mode |

-------|-------------|
| `==` | Auto‑indent line |
| `V + ==` | Indent selected lines |

---

## Searching

Searching helps you quickly find text in large files.

### Forward Search `/`
```
/printf
```
- Press `n` → next match
- Press `N` → previous match

### Backward Search `?`
```
?main
```
- Press `n` → backward
- Press `N` → forward

| Shortcut | Description |
|---------|-------------|
| `*` | Search word under cursor forward |
| `#` | Search word under cursor backward |

-------|-------------|
| `/text` | Search forward |
| `?text` | Search backward |
| `n / N` | Next / previous result |
| `*` | Search word under cursor forward |
| `#` | Search word under cursor backward |

---

## Search & Replace
| Command | Description |
|-------|-------------|
| `:%s/old/new/g` | Replace in whole file |
| `:s/old/new/g` | Replace in selection |

---

## Navigation
| Command | Description |
|-------|-------------|
| `:1` / `1G` / `gg` | First line |
| `:$` / `G` | Last line |
| `[[` | Start of file |
| `]]` | End of file |
| `zz` | Center cursor |

---

## Undo & Redo

Undo and redo changes efficiently.

| Command | Description | Example |
|--------|-------------|---------|
| `u` | Undo last change | `5u` undo 5 steps |
| `Ctrl+r` | Redo change | `3Ctrl+r` redo 3 |
| `:undolist` | View undo tree | Shows history |
| `:earlier` | Go back in time | Undo older state |
| `:later` | Go forward in time | Redo state |
| `:e!` | Revert to last save | Discard edits |

-------|-------------|
| `u` / `5u` | Undo |
| `Ctrl+r` / `3Ctrl+r` | Redo |
| `:undolist` | Undo tree |
| `:earlier` / `:later` | Navigate undo tree |
| `:e!` | Revert to last save |

---

## Deletion

Deletion commands also act as **cut** operations.

| Command | Description | Example |
|-------|-------------|---------|
| `dd` | Delete current line | `5dd` deletes 5 lines |
| `dw` | Delete word | Deletes word after cursor |
| `daw` | Delete word incl. space | Useful for cleanup |
| `diw` | Delete inside word | Cursor inside word |
| `D` | Delete to end of line | Like `d$` |
| `d0` | Delete to line start | Removes left side |
| `di"` | Delete inside quotes | "Hello World" |
| `dt;` | Delete till `;` | Stops before `;` |

-------|-------------|
| `dd` / `5dd` | Delete lines |
| `dw` | Delete word |
| `d$` | Delete to end of line |
| `d0` | Delete to start |
| `di"` | Delete inside quotes |
| `d%` | Delete bracket block |

---

## Change Commands
| Command | Description |
|-------|-------------|
| `cc` | Change line |
| `ciw` | Change word |
| `ci"` | Change inside quotes |
| `C` | Change after cursor |

---

## Visual Modes

Visual modes allow selecting text blocks.

| Mode | Command | Description |
|-----|--------|-------------|
| Visual | `v` | Select characters |
| Visual Line | `V` | Select whole lines |
| Visual Block | `Ctrl+v` | Column selection |

-------|-------------|
| `v` | Visual mode |
| `V` | Visual line mode |
| `Ctrl+v` | Visual block mode |

---

## Copy & Paste (Yank & Put)

| Command | Description | Example |
|--------|-------------|---------|
| `y` | Yank selection | Copy text |
| `Y` | Yank whole line | Line copy |
| `yi"` | Yank inside quotes | Copy text only |
| `yi(` | Yank inside brackets | `()` `{}` `[]` |
| `yt,` | Yank till `,` | Stops before char |
| `p` | Paste after cursor | Default paste |
| `P` | Paste before cursor | Above line |
| `10p` | Paste multiple times | Repeat paste |

-------|-------------|
| `y` | Yank (copy) |
| `Y` | Yank line |
| `yi"` | Yank inside quotes |
| `p / P` | Paste after / before |
| `10p` | Paste 10 times |

---

## Replace

| Command | Description | Example |
|--------|-------------|---------|
| `r<char>` | Replace single character | `ra` replaces with `a` |

-------|-------------|
| `r<char>` | Replace character |

---

## Marks & Jumps

Marks let you save and jump to positions.

| Command | Description | Example |
|--------|-------------|---------|
| `ma` | Mark current position as `a` | Save location |
| `'a` | Jump to mark `a` | Exact line jump |

-------|-------------|
| `ma` | Mark position `a` |
| `'a` | Jump to mark |

---

## Macros

Macros record and replay sequences of commands.

### Record Macro
```vim
qa          " start recording macro a
d3wA100<Esc>
q           " stop recording
```

### Use Macro
```vim
@a          " run macro once
5@a         " run macro 5 times
```

-------|-------------|
| `qa` | Start recording macro `a` |
| `q` | Stop recording |
| `@a` | Run macro |

---

## Vim Configuration

**Configuration file:** `~/.vimrc`

```vim
:set number
:set relativenumber
:set mouse=a
:set tabstop=4
:colorscheme desert
```

### Vim Plugins
- Vim-Plug
- Pathogen
- Vundle

Use plugins to extend Vim features.

