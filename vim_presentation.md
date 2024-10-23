# VIM Presentation for Lava Lamp Lab
## What is vim 
Is a CLI based model text editor.

                                       VIM - Vi IMproved

                                        version 8.2.2121
                                    by Bram Moolenaar et al.
                             Modified by team+vim@tracker.debian.org
                           Vim is open source and freely distributable

                                  Help poor children in Uganda!
                         type  :help iccf<Enter>       for information

                         type  :q<Enter>               to exit
                         type  :help<Enter>  or  <F1>  for on-line help
                         type  :help version8<Enter>   for version info

## vim the program vs vim motions
- You can separate vim the editor from the motions how you navigate and edit text in vim.
- You don't need to use vim the editor to benefit from learning vim as most text editor have plugins that allow you to use vim motions within it. E.g. [VS Code](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim).
- I am going to be focusing on the aspects of vim is more centered around vim motions rather than specifics to vim the editor 
- Also thanks to ThePrimeagen for introducing me to vim and check out his playlist [VIM as your editor](https://www.youtube.com/watch?v=X6AR2RMB5tE&list=PLm323Lc7iSW_wuxqmKx_xxNtJC_hJbQ7R) 

# Modes
## Normal mode
- This is the mode where you can move you cursor.
- As a general rule you want to return to normal mode after you have finished what you where doing in the other modes.

## Insert mode
- This is the mode where you can type like any other editor.
- You can enter insert in the following ways

| Key     | Behavior                                                                                          |
| :-----: | :------------------------------------------------------------------------------------------------ |
|  i      | Goes in the insert mode before or to the left of your cursor's current position.                  |
|  a      | Goes in the insert mode after or to the right of your cursor's current position.                  |
|  I      | Goes in the insert mode at the start of your cursor's current line.                               |
|  A      | Goes in the insert mode at the end of your cursor's current line.                                 |
|  o      | Goes in the insert mode at a new line below your cursor's current line.                           |
|  O      | Goes in the insert mode at a new line above your cursor's current line.                           |
|  s      | Deletes current character and enters insert mode.                                                 |
|  S      | Deletes current line and enters insert mode.                                                      |
| `<Esc>` | Exits insert mode.                                                                                |
| `<c-[>` | Exits insert mode.                                                                                |
| `<c-c>` | Exits insert mode. Has some weird behavior that the other 2 ways of exiting insert does not have. |

### how to exit insert mode
- You can exit insert mode by pressing `<Esc>` or a custom binding like what I have where it is `jj`

## Command mode
- The command mode is entered by pressing `:`, a command is submitted with `<Enter>` and exited with `<Esc>`.
### Useful commands
| Command         | Behavior                                                               |
| :-------------: | :--------------------------------------------------------------------- |
| :w              | Saves current buffer (file).                                           |
| :w `<filename>` | Saves current buffer as the specified file.                            |
| :q              | Exits vim. Alternatively you can reboot your computer to exit VIM :> . |
| :wq             | Saves current buffer (file) and exits vim.                             |
| :123            | Goes to the line number (123 in this case).                            |

## Visual mode
- Is a mode where you can select parts of your file and it is highlighted.
- Like dragging your move over text to select it.
### Visual line mode
- Exactly like visual mode but selects entire lines
- Demo here:
```
Lorem ipsum dolor sit amet, officia excepteur ex fugiat reprehenderit enim labore culpa sint ad nisi Lorem pariatur mollit ex esse exercitation amet. Nisi anim cupidatat excepteur officia.
Reprehenderit nostrud nostrud ipsum Lorem est aliquip amet voluptate voluptate dolor minim nulla est proident.
Nostrud officia pariatur ut officia.
```
### Visual block mode 
- Like visual mode makes a selection as a block enabling inserts over multiple lines
- Demo here:
```
    *********** -----------------
    *********** -----------------
    *********** -----------------
    *********** -----------------
    *********** -----------------
    *********** -----------------
    *********** -----------------
```
### Key bindings
| Key      | Behavior                                                                          |
| :------: | :-------------------------------------------------------------------------------- |
|  v       | Enters and exits visual mode.                                                     |
|  V       | Enters and exits visual Line mode.                                                |
| `<C-v>`  | Enters and exits visual block mode.                                               |
|  o       | Changes your cursor's position to the start or the end of your current selection. |

# Operators, Counts, & Motions
## Very basic Motions
- h j k l function similarly to arrow, this is very useful when needing to move the cursor one character at a time.
      ↑
      k
  ← h . l  →
      j
      ↓
- To go faster ⚡ there are motions.

| Key | Behavior                                                                    |
| :-: | :-------------------------------------------------------------------------- |
|  w  | Moves to the start of the next word.                                        |
|  e  | Moves to the end of the next word.                                          |
|  b  | Moves back to the start of the previous word.                               |
|  W  | Moves to the start of the next word separated only by white space.          |
|  E  | Moves to the end of the next word separated only by white space.            |
|  B  | Moves back to the start of the previous word separated only by white space. |

## Count
- If you type a number your next motion will be performed that amount of times.
- So if you type `20k` you will move up 20 times, this is why people that use vim tend use relative line numbers.
- This can also be done for other non motions operators like inserts and macros e.g. `20iwhat you entered<Esc>` with insert what you entered 20 times.

## Operators
| Key     | Behavior                                                                        |
| :-----: | :------------------------------------------------------------------------------ |
| y       | Copy or Yanks text selected by the following motion.                            |
| Y       | Copy or Yanks until to end of the line                                          |
| d       | Deletes text selected by the following motion.                                  |
| D       | Deletes until the end of the line.                                              |
| c       | Deletes text selected by the following motion and then goes into insert mode.   |
| C       | Deletes until the end of the line and then goes into insert mode.               |
| >       | Indents the selection.                                                          |
| <       | Un-indents the selection.                                                       |
| =       | Formats the text selected by the following motion.                              |
| gu      | Lowercases the selection.                                                       |
| gU      | Uppercases the selection.                                                       |
| ~       | Toggle case (only current char use visual mode to toggle a selection).          |
| .       | Does the previous operation.                                                    |
| u       | Undo.                                                                           |
| `<c-r>` | Redo.                                                                           |
| x       | Deletes current character.                                                      |
| r       | Replaces current character with next entered character.                         |
| J       | Merge the next line with the current one.                                       |

- Deleting and yanking goes to the same register.

## Horizontal motions

| Key | Behavior                                                                                |
| :-: | :-------------------------------------------------------------------------------------- |
| _   | Go to the first non white space character of the line.                                  |
| ^   | Go to the first non white space character of the line.                                  |
| 0   | Go to the first character of the line.                                                  |
| $   | Go to the end of the line.                                                              |
| g_  | Go to the end of the line.                                                              |
| f   | Go to the next instance of character that you enter next.                               |
| F   | Go to the previous instance of character that you enter next.                           |
| t   | Go to the character before next instance of character that you enter next.              |
| T   | Go to the character before previous instance of character that you enter next.          |
| ;   | Go to the next instance of the character or before the character lasts used by f/t.     |
| ,   | Go to the previous instance of the character or before the character lasts used by f/t. |

## Vertical motions
| Key       | Behavior                                                                            |
| :-------: | :---------------------------------------------------------------------------------- |
| {         | Moves up to the top of the current contiguous block of text or paragraph.           |
| }         | Moves down to the bottom of the current contiguous block of text or paragraph.      |
| `<c-u>`   | Moves up half a page.                                                               |
| `<c-d>`   | Moves down half a page.                                                             |
| /         | Prompts for a search pattern and then finds the next instance of it.                |
| ?         | Prompts for a search pattern and then finds the previous instance of it.            |
| n         | Finds the next instance of the search pattern.                                      |
| N         | Finds the previous instance of the search pattern.                                  |
| *         | Adds the current word as the search pattern and finds the next instances of it.     |
| #         | Adds the current word as the search pattern and finds the previous instances of it. |
| %         | Jumps to the matching pair for brackets [], parentheses (), etc.                    |

# Text objects
- When using operators or in visual mode you can use text object do a selection based on predefined patterns.
- Each text object has to different selections around using `[command] -> a -> [text object]` or inside the selection `[command] -> i -> [text object]`.

| Key     | Behavior                                                                                                                     |
| :-----: | :--------------------------------------------------------------------------------------------------------------------------- |
| w       | Selects the current word. `i` selects only the word and `a` includes white-space.                                            |
| W       | Selects the current word by only using white-space as the delimiter. `i` selects only the word and `a` includes white-space. |
| s       | Selects the current sentence. `i` selects only the sentence and `a` includes white-space.                                    |
| p       | Selects the current paragraph or contiguous text. `i` selects only the paragraph and `a` includes the empty newline(s).      |
| t       | Selects the current xml tag. `i` selects the content inside the tag and `a` includes the tag.                                |
| (/)     | Selects the current parentheses. `i` selects the content inside the parentheses and `a` includes the parentheses.            |
| [/]     | Selects the current brackets. `i` selects the content inside the brackets and `a` includes the brackets.                     |
| {/}     | Selects the current braces. `i` selects the content inside the braces and `a` includes the braces.                           |
| '       | Selects the current single quotes. `i` selects the content inside the single quotes and `a` includes the single quotes.      |
| "       | Selects the current braces. `i` selects the content inside the braces and `a` includes the braces.                           |

- Demo here:
```
Lorem ipsum dolor sit amet, officia excepteur ex fugiat reprehenderit enim labore culpa sint ad nisi "Lorem pariatur mollit ex" esse exercitation amet. Nisi anim cupidatat excepteur officia.
Reprehenderit nostrud nostrud ipsum Lorem est aliquip amet voluptate voluptate dolor minim nulla est proident.
Nostrud officia pariatur ut officia.
Sit irure elit esse ea nulla sunt ex occaecat reprehenderit commodo officia dolor Lorem duis laboris cupidatat officia voluptate.
Culpa proident adipisicing id nulla nisi laboris ex in Lorem sunt duis officia eiusmod.
Aliqua reprehenderit commodo ex non excepteur duis sunt velit enim.
Voluptate laboris sint cupidatat ullamco ut ea consectetur et est culpa et culpa duis.
<p><span>Hi</span> mom</p>
```

# Macros
- When you need to redo some complex set of vim edits you can make use of VIM's macro engine to do so.
- To use it you press `q` and any other letter to select a register to enter recording mode.
- Then you can perform the action and press `q` to save the recording. Note that you should perform the macro in a way that it will work for all the places you want to use it.
- Then you can press `@` and the letter of the register that has the macro to execute the macro or `@@` to execute the same macro. You can also add a count to the macro to execute it multiple times e.g. `21@q`.
- Note that this is the same register used for yanking. I just use `qq` as it is the simplest and then I know that the register is reserved for macros.

Demo:
```
[
    all: {value: "0"},
    the: {value: "1"},
    objects: {value: "2"},
    in: {value: "3"},
    this: {value: "4"},
    array: {value: "5"},
    are: {value: "6"},
    redundant: {value: "7"},
]
```

# Jump list
- Certain motions add the location of the cursor to what is known a jump list allowing you to jump back to that location.
- `<c-o>` goes back on the jump list `<c-i>` jumps forward on the jump list.

# Marks
- One can also leave marks at specific cursor locations and then jump back to that location at when you want to.
- Marks are set by pressing `m` followed by any character. An important thing to know is that marks using lowercase characters are limited in scope to the current file and uppercase works between files.
- You can then jump to that mark using back tick (\`) to jump to the exact location and `'` to jump the line.

# Custom bindings
- Vim also supports custom binding allowing you to simply inputs or make the inputs feel for you.
- Some bindings that I use:

| Mode | Key         | What it map to    | Descr                                                                                         |
| :--- | :---------: | :---------------: | --------------------------------------------------------------------------------------------- |
| i    | jj          | `<Esc>`           | Makes that I can exit insert mode using my strongest finger 👆💪.                             |
| nv   | `<space>d`  | "\_d              | Makes that I can delete without copying. You can make also just bind this to `d` if you want. |
| n    | `<c-v>`     | "+p               | Pastes from the system clipboard.                                                             |
| nv   | `<space>vb` | `<c-v>`           | Goes into visual block mode as I have that bound to paste.                                    |
| n    | `<space>o`  | `moo<Esc>\``     | Creates an empty new line below the cursors position.                                         |
| n    | `<space>O`  | `moO<Esc>\``     | Creates an empty new line above the cursors position.                                         |




                                                                         ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣀⣀⣀⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⡏⡀⠀⢄⠈⢙⢒⠲⢦⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣠⠶⠚⠃⢣⠀⠸⣶⠋⢈⠇⣿⣷⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⢀⣠⠤⢄⡀⠀⠀⢀⣤⣶⢖⣿⣏⡷⠰⠞⠉⠉⢺⣇⠀⢹⠀⢸⡀⠋⢿⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⣠⠤⠶⣚⣋⡅⠀⠀⠙⣻⡟⠋⡔⠛⠉⠁⠙⣷⠀⠰⣿⡄⠀⢻⡆⠀⢧⠀⠙⢦⠀⡿⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⢸⣯⡵⠛⠛⠉⠈⣷⠀⠘⠉⠀⠙⢦⡀⠀⣾⣆⠀⢻⣇⠀⢳⣳⡀⠘⣷⣀⣨⠙⢲⣒⣤⢣⠇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣄⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⢸⡿⡇⢴⠀⠀⣿⠈⣇⠀⢸⣣⡀⠘⣧⡀⠙⠿⠀⠈⣿⣄⣸⡏⢻⣾⣥⢨⣿⣿⠿⠛⠛⠉⠀⠀⣀⣤⣤⠤⠤⣒⡲⠤⠤⣤⣤⣤⣤⣀⡀⢧⡀⢹⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠙⠻⡆⢧⠀⠹⡄⢹⡄⠘⢏⢧⠀⢸⡷⣤⣤⣶⣚⠋⢸⠛⢳⣿⡅⠘⢇⢷⣿⠀⠀⣤⢔⣻⡯⠶⠛⠛⠋⠉⠉⠉⠉⣉⣉⣛⡛⠓⢲⣬⡝⣷⣤⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⢿⡘⡆⠀⢻⠀⢳⣄⣼⠛⢳⣾⢥⣴⠛⠉⠁⠉⢻⡄⠈⢣⢣⠀⠸⡎⠈⣧⣯⡾⠋⠁⠀⣠⣤⣴⣾⣿⣿⣿⣿⠿⢛⣭⣴⣿⡿⠟⠋⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⢧⡛⠀⠚⢰⣿⣿⠛⠳⣼⡇⠀⣿⠀⠘⣟⡄⠈⢳⡀⠘⠿⠃⢠⡇⣠⣿⠛⢀⣤⣾⣿⣿⣿⣿⣿⡿⠟⣫⣤⣞⡯⠚⠋⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠉⠛⠪⠖⢻⣝⣦⠀⠘⠇⠀⡟⣦⠀⠛⠿⠀⡼⠓⡦⠤⠴⣫⣤⣿⡁⣠⣿⣿⣿⣿⣿⡿⢿⣡⡴⣿⡭⠛⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠙⢎⠳⡄⠀⠀⡇⢈⣓⣦⡴⢛⡥⣺⡿⠿⢿⣿⣿⠁⣵⣿⣿⣿⡿⠟⣡⣴⣿⣳⣛⣧⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⠤⠒⢦⣀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢳⠈⠆⠀⡧⢸⣿⠛⠛⠛⠛⠁⠀⣠⣾⣿⠃⣼⣿⣿⣿⢋⣴⠞⠋⠀⠴⠿⠿⣿⣯⣹⣀⣀⣀⡀⠀⠀⠀⠀⠀⣘⣦⣤⣀⠈⠑⢦⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⣇⠀⣴⣃⡬⣿⣁⡀⠀⠀⠀⣼⣿⢿⡇⡴⠋⠀⣻⡿⠛⠁⠀⠀⠀⠀⠀⠀⠉⢙⣶⡿⠿⠿⠭⣍⣒⣶⢤⣀⣏⣀⠉⠓⣝⡄⠈⢧⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠲⢷⡿⠋⢉⣿⠀⢀⣞⡿⠃⠸⠃⠀⠀⠀⠈⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠙⢦⣤⣀⣀⡀⠈⠉⠳⢮⣝⠯⣶⡀⠈⣿⠦⠼⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣀⣀⣀⣰⡟⠀⣰⡿⠋⢹⣿⣿⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠠⣿⣿⣿⣿⣿⣷⣶⣄⡀⠉⠳⣝⢿⡉⠁⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⠀⠀⣀⣤⣾⣽⣿⣿⣏⣿⠀⠀⣿⠁⢠⣿⢻⠇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣝⠿⣿⣿⣿⣿⣿⣿⣷⣄⠘⢷⣙⣄⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⣠⣾⡿⠞⠉⠸⢏⣾⡟⠉⢷⡀⣿⣦⣼⣿⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⡿⣶⣌⡙⠿⣿⣿⣿⣿⣿⣷⣄⠻⣍⢦⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⣠⣾⡿⠋⠀⠀⠀⠀⢸⣿⡇⠀⠈⢉⣿⢿⣿⣫⣿⠀⠀⠀⠀⠀⣀⠀⠀⠀⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣾⣱⠁⠙⠯⢿⡶⣤⣉⡻⠿⣿⣿⣿⣦⠙⣮⢦⠀⠀⠀
                                                                        ⠀⠀⠀⣴⣿⠟⠀⠀⠀⠀⠀⠀⠘⣟⣇⣀⣶⡯⠟⠋⠉⠀⢹⣆⠀⠀⠀⠀⠻⣦⣄⣀⣤⡶⠀⠀⠀⠀⠀⢐⠶⢀⣴⣿⠁⠀⠀⠀⠀⠉⠙⠯⢽⣷⡶⣍⣙⠻⣷⠈⢯⣣⡀⠀
                                                                        ⠀⠀⡼⣿⠃⠀⠀⠀⠀⠀⠀⠀⠀⠹⣾⣿⣋⠀⠀⠀⠀⠀⠀⢻⣆⠀⠀⠀⠀⠈⠉⠉⠁⠀⠀⠀⢀⣀⠀⠘⠷⠛⣿⣹⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠉⠙⠻⢿⣶⣤⣜⢯⣣⡀
                                                                        ⠀⢸⣿⠃⢰⠀⣀⠀⠀⠀⠀⠀⠀⠀⠘⣿⠖⠀⠀⠀⠀⠀⠀⠀⢹⣷⣤⡀⠀⠀⠀⠀⣷⣄⣀⣀⣈⡉⣀⡀⠀⢠⡿⡟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠛⠿⣟⠇⠇
                                                                        ⢀⣿⡟⠀⠀⠀⣿⠀⢰⣇⠀⡴⠂⠀⢰⡏⠀⠀⠀⠀⠀⠀⠀⣰⠏⠀⠉⠛⠶⣤⣤⡀⠀⠉⠉⠁⠈⠙⢋⣠⣴⣿⠟⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠉⠁
                                                                        ⢸⣿⡇⠀⠀⠀⠻⣄⣸⠙⢦⡀⠀⠀⢸⣇⠀⠀⠀⠀⠀⠀⢰⡏⠀⠀⠀⠀⠀⠀⠀⠉⠛⠛⠛⠛⠛⠛⢿⣷⡟⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⢸⣿⡇⠀⠀⠀⠀⠙⠋⠀⠀⠹⠀⠀⢸⡿⣦⠀⠀⠀⠀⠀⡟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⡇⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠸⣿⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣾⠁⠈⢷⣄⢀⣄⢰⣷⢠⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣴⡟⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⢹⣿⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⡿⠀⠀⠀⠙⠟⣿⣿⠻⣿⣇⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⣿⡿⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⢷⣿⣆⠀⠀⠀⠀⠀⠀⠀⠀⠘⣧⠀⠀⠀⠀⠀⠲⣿⠀⠉⠹⣿⣦⠀⠀⠀⠀⠀⠀⢀⡀⢀⣰⣷⠎⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠙⢟⣷⣄⡀⠀⠀⠀⠀⠀⠀⢻⡆⠀⠀⠀⠀⠀⢹⣇⠀⠀⠈⢙⣿⣷⡀⠀⢀⣴⣿⣴⣟⡟⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠙⠿⢟⣶⣤⣄⣀⣀⣀⣨⣿⣦⣀⣀⣀⣀⣀⣿⡄⠀⠀⠈⠉⣿⣿⡶⠛⠉⠀⣾⡝⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⠀⠀⠉⠁⠒⠚⠛⠓⠊⠉⠿⣿⣿⡋⢹⡁⣸⢷⡄⠀⠀⠀⠸⣆⣀⠀⠀⣾⣽⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠑⠯⠭⠭⠭⢽⣿⣦⡀⠰⣄⢺⣿⣆⣾⣽⣻⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
                                                                        ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠙⠚⠛⠲⣻⣛⣿⡿⣿⣾⡏⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀



