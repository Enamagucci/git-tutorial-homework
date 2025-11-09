# Navigating the Command Line

- Shell: An interactive layer which provides an environment to interact with the Operating System through various commands
- Terminal: A program which creates a shell instance
- Directory: A structure which holds all your files or other directories; is known as Folders from a Windows File Explorer 

## Basic Bash Commands
- `ls`: List the files and sub-directories within the current directory
- `ls -a`: List all the content in a directory including hidden files such as dotfiles (`.config`, `.ssh`)
- `mv [source] [target]`: Move a file or directory to another location e.g
    ```sh
    # Moves myfile.txt into the code directory
    mv myfile.txt ~/code
    ```
- `cp [source] [target]`: Copy a file to another location 
- `cp -r [source][ target]`: Copy a directory to another location
- `cat`: Print the contents of a file