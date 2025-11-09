# Vim 

- Vim is command line based text editor that provides an alternative and keyboard-centric way of navigating and editting a file.
- It can be useful for quickly editting a text file without opening a bloated text file
- Alternatives for quick edits can be `Nano` or using [`echo` to append to a file](./cli_basics.md)

## The Basics

- Open a file in vim using:
    ```
    vim myfile.txt
    ```

### Modes

- Normal Mode: Navigate through the next file; This is the default mode and can be entered by pressing `ESC`
  - Up: `k`
  - Down: `j`
  - Left: `h`
  - Right: `l`
  - Deleting a Line: `dd`
  - Deleting a character at the cursor: `x`
  - Undo: `u`
  - Redo: `ctrl+r`
  - Move to beginning of line: `0`
  - Move to end of line: `$`
  - Move to end of line and enter insert mode: `A`
  - Move to top of file `gg`
  - Move toe end of file `G`

- Visual Mode: Allows you to select text from the point of the cursor. Can be entered by pressing `v`
  - Select from Entire Line: `V`

- Command Mode: Can be enterd by pressing `:`

 ### Further Reading

 - I recommend reading [beyond the basics](https://www.youtube.com/watch?v=z4eA2eC28qg) if you want to really use Vim in your development environment 