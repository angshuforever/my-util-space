# Vim Command Cheatsheet

## Table of Contents
1. [Basic Navigation](#basic-navigation)
2. [Inserting Text](#inserting-text)
3. [Editing Text](#editing-text)
4. [Deleting Text](#deleting-text)
5. [Copying and Pasting](#copying-and-pasting)
6. [Searching and Replacing](#searching-and-replacing)
7. [Working with Multiple Files](#working-with-multiple-files)
8. [Vim Modes](#vim-modes)
9. [Saving and Exiting](#saving-and-exiting)
10. [Advanced Commands](#advanced-commands)

## Basic Navigation

### Moving the Cursor

| Command | Description | Example |
|---------|-------------|---------|
| `h` | Move cursor left | `3h` moves cursor 3 positions left |
| `j` | Move cursor down | `5j` moves cursor 5 lines down |
| `k` | Move cursor up | `2k` moves cursor 2 lines up |
| `l` | Move cursor right | `4l` moves cursor 4 positions right |
| `w` | Move to start of next word | `3w` moves forward 3 words |
| `b` | Move to start of previous word | `2b` moves back 2 words |
| `e` | Move to end of word | `3e` moves to end of third word forward |
| `0` | Move to start of line | `0` jumps to first character of line |
| `$` | Move to end of line | `$` jumps to last character of line |
| `gg` | Move to first line of document | `gg` jumps to first line |
| `G` | Move to last line of document | `G` jumps to last line |

**Explanation**: These commands form the core of Vim navigation. Combining them with numbers allows for quick and precise movement around your document.

## Inserting Text

| Command | Description | Example |
|---------|-------------|---------|
| `i` | Insert before cursor | `iHello` inserts "Hello" before cursor |
| `a` | Insert after cursor | `aWorld` inserts "World" after cursor |
| `I` | Insert at beginning of line | `IStart: ` inserts "Start: " at line start |
| `A` | Insert at end of line | `AEnd.` inserts "End." at line end |
| `o` | Open new line below | `oNew line` adds "New line" on new line below |
| `O` | Open new line above | `OAbove` adds "Above" on new line above |

**Explanation**: These commands switch Vim from Normal mode to Insert mode, allowing you to add text. Press `Esc` to return to Normal mode.

## Editing Text

| Command | Description | Example |
|---------|-------------|---------|
| `r` | Replace single character | `ra` replaces character under cursor with 'a' |
| `R` | Replace multiple characters | `RHello` overwrites next 5 characters with "Hello" |
| `cw` | Change word | `cwhello` deletes word and inserts "hello" |
| `cc` | Change entire line | `ccNew line content` replaces line with "New line content" |
| `C` | Change to end of line | `CEnd of line` changes from cursor to end of line |
| `~` | Switch case of character | `~` on 'a' changes it to 'A' and vice versa |
| `u` | Undo last change | `u` undoes the last edit |
| `Ctrl + r` | Redo last undone change | `Ctrl + r` redoes the last undone edit |

**Explanation**: These commands allow for quick edits and modifications to your text. The change commands (`c`) delete specified text and enter Insert mode.

## Deleting Text

| Command | Description | Example |
|---------|-------------|---------|
| `x` | Delete character under cursor | `3x` deletes 3 characters from cursor |
| `X` | Delete character before cursor | `2X` deletes 2 characters before cursor |
| `dw` | Delete word | `d3w` deletes 3 words |
| `dd` | Delete entire line | `5dd` deletes 5 lines |
| `D` | Delete to end of line | `D` deletes from cursor to end of line |

**Explanation**: Delete commands remove text without entering Insert mode. Deleted text is stored in a register and can be pasted.

## Copying and Pasting

| Command | Description | Example |
|---------|-------------|---------|
| `yy` | Yank (copy) entire line | `3yy` copies 3 lines |
| `yw` | Yank word | `y3w` copies 3 words |
| `y$` | Yank to end of line | `y$` copies from cursor to end of line |
| `p` | Paste after cursor | `p` pastes copied or deleted text after cursor |
| `P` | Paste before cursor | `P` pastes copied or deleted text before cursor |

**Explanation**: "Yanking" is Vim's term for copying. Pasting can be done multiple times, and Vim remembers multiple deleted or yanked texts.

## Searching and Replacing

| Command | Description | Example |
|---------|-------------|---------|
| `/pattern` | Search forward for pattern | `/hello` searches for next "hello" |
| `?pattern` | Search backward for pattern | `?world` searches for previous "world" |
| `n` | Repeat search in same direction | `n` finds next occurrence of search |
| `N` | Repeat search in opposite direction | `N` finds previous occurrence of search |
| `:%s/old/new/g` | Replace all occurrences in file | `:%s/cat/dog/g` replaces all "cat" with "dog" |
| `:s/old/new/g` | Replace all occurrences in line | `:s/yes/no/g` replaces all "yes" with "no" in current line |

**Explanation**: Searching allows quick navigation to specific text. The replace command (`:%s`) is powerful for making multiple changes at once.

## Working with Multiple Files

| Command | Description | Example |
|---------|-------------|---------|
| `:e filename` | Edit a file in a new buffer | `:e newfile.txt` opens newfile.txt |
| `:bnext` or `:bn` | Go to next buffer | `:bn` switches to next file |
| `:bprev` or `:bp` | Go to previous buffer | `:bp` switches to previous file |
| `:bd` | Delete a buffer (close a file) | `:bd` closes current file |
| `:sp filename` | Open a file in a horizontal split | `:sp config.ini` opens config.ini in split window |
| `:vsp filename` | Open a file in a vertical split | `:vsp index.html` opens index.html in vertical split |
| `Ctrl + ws` | Split windows horizontally | `Ctrl + ws` splits current window horizontally |
| `Ctrl + wv` | Split windows vertically | `Ctrl + wv` splits current window vertically |
| `Ctrl + ww` | Switch between windows | `Ctrl + ww` moves cursor to next window |
| `Ctrl + wq` | Quit a window | `Ctrl + wq` closes current window |

**Explanation**: These commands allow you to work with multiple files and split your screen to view different parts of your document or different files simultaneously.

## Vim Modes

| Mode | Description | How to Enter |
|------|-------------|--------------|
| Normal | Default mode for navigation and commands | Press `Esc` from any other mode |
| Insert | For inserting text | Press `i`, `a`, `o`, etc. from Normal mode |
| Visual | For selecting text | Press `v` for character-wise, `V` for line-wise, or `Ctrl + v` for block-wise selection |
| Command | For entering Vim commands | Press `:` from Normal mode |

**Explanation**: Vim's different modes allow it to interpret your keystrokes differently based on what you're trying to do, making it very powerful and efficient.

## Saving and Exiting

| Command | Description | Example |
|---------|-------------|---------|
| `:w` | Save changes | `:w` saves the current file |
| `:w filename` | Save as a specific filename | `:w backup.txt` saves current content as backup.txt |
| `:wq` or `:x` | Save changes and exit | `:wq` saves and quits Vim |
| `:q` | Quit (fails if there are unsaved changes) | `:q` quits if no unsaved changes |
| `:q!` | Quit and discard unsaved changes | `:q!` quits without saving changes |
| `ZZ` | Save and quit | `ZZ` in Normal mode is equivalent to `:wq` |

**Explanation**: These commands allow you to save your work and exit Vim. Using `:q!` discards all unsaved changes, so use it carefully.

## Advanced Commands

| Command | Description | Example |
|---------|-------------|---------|
| `.` | Repeat last command | `.` repeats the last change made |
| `>` | Indent text | `>G` indents from cursor to end of file |
| `<` | Unindent text | `<5j` unindents 5 lines down |
| `=` | Auto-indent text | `=G` auto-indents from cursor to end of file |
| `gg=G` | Auto-indent entire file | `gg=G` in Normal mode indents the whole file |
| `Ctrl + n` | Auto-complete word | In Insert mode, `Ctrl + n` auto-completes based on words in file |
| `q{register}` | Record a macro | `qa` starts recording macro in register 'a' |
| `@{register}` | Play a macro | `@a` plays macro recorded in register 'a' |

**Explanation**: These advanced commands showcase some of Vim's more powerful features, including repeating commands, managing indentation, and recording macros for complex, repetitive tasks.

Remember, Vim is highly customizable and has many more commands and features. This cheatsheet covers the most commonly used commands to get you started or serve as a quick reference.
