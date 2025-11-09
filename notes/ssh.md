# SSH 
- SSH (Secure Shell) allows you communicate securely to a remote computer over an open and insecure network (the Internet)
- In the context of GitHub it allows you to connect to your remote repositories and allows you to authenticate with private/public keys

## Generating Keys to Authenticate to GitHub

Assuming you are using Git Bash as instructed:

### Pre-Requisite

- [Basic CLI Navigation](./cli_basics.md)    
- Download Git Bash if you are on Windows: https://git-scm.com/install/
- Create a directory in your home directory `~/.ssh` and enter it

### 1. Start Up the SSH Key Manager

 - Ensure the SSH Key Manager is running with:
    ```sh
    eval $(ssh-agent)
    ```
 - The expected output would be the running process id of the ssh-agent

    ```sh
    Agent pid 1234
    ```

### 2. Generate a new Private/Public Key

 - Create an encrypted private/public key pair using your GitHub email address. The recommended encryption algorithm is `ed25519`.

    ```sh
    ssh-keygen -t ed25519 -C "myemail@email.com"
    ```

 - The ouput will take you through a series of prompts
    ```
    Enter file in which to save the key(/home/user/.ssh/id_ed25519):
    ```

- Ideally you'd want to name this key pair `github` to identify what it is used for 

- You will then be prompted for a password which can be left empty for this tutorial

- The following files will be created `/.ssh/github` and `/.ssh/github.pub` representing the private and public key respectively

- Copy the content of the public key, `github.pub` and save it for the next step.

### 3. Adding the Key to the Key Manager

- Add the private key to the `ssh-agent` with:

    ```sh
    ssh-add github
    ```

### 4. Create an SSH config file

- An SSH Config file allows you to define certain settings such as saving Hosts and keys related to them

- Create the file ~/.ssh/config

- Add the following content to the file:
    ```sh
    Host github.com
        HostName github.com
        User git
        IdentityFile ~/.ssh/github
    ```

### 4. Adding The Key to GitHub

- Navigate to your GitHub Account Settings > SSH and GPG Keys   

- Click the 'New SSH Key' Button

- Give it a memorable Title e.g. "My Personal Desktop"

- Paste the content of your public key in the Textbox


### 5. Testing the Key

- In your terminal run the following to test the connection to GitHub:

    ```sh
    ssh -T git@github.com
    ```


## Troubleshooting

- If you are using Git Bash's implementation of OpenSSH the Key Manager may have to be reset on each start up of the terminal.

    - Solution A - Carry on using OpenSSH

        1. Create a `.bashrc` file in your user directory

        2. Add the following lines:
            ```sh
            eval $(ssh-agent)
            ssh-add ~/.ssh/github
            ```

        3. These commands should run automatically each time a new shell instance starts up