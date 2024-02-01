# Table of Contents

- [Xcode](#xcode)
- [Homebrew](#homebrew)
- [Terminal](#terminal)
- [Git](#git)
- [Visual Studio Code](#visual-studio-code)
- [Node.js](#nodejs)

# Xcode

Open Terminal and run the following command:

```
xcode-select --install
```

Verify that you've successfully installed Xcode Command Line Tools:

```sh
xcode-select -p
```

The output should be the following: `/Library/Developer/CommandLineTools`

# Homebrew

To install **Homebrew**, simply run the installation command provided on their [website](https://brew.sh/) within the terminal.

Follow & execute the `Next steps` shown inside the Terminal.

Check everything is working with:

```sh
brew doctor
```

The output should be the following: `Your system is ready to brew.`

# Terminal

## Oh My Zsh

Install [Oh My Zsh](https://ohmyz.sh/#install).

## Theme

Install [Powerlevel10k](https://github.com/romkatv/powerlevel10k) for Oh My Zsh.

# Git

macOS comes with a pre-installed version of Git, but we'll install our own through Homebrew to allow easy upgrades and not interfere with the system version. To do so, simply run:

```sh
brew install git
```

Restart the terminal.

When done, check that the version is >= 2.28 :

```sh
git --version
```

Next, we'll define our Git user :

```sh
git config --global user.name "Your Name Here"
```

```sh
git config --global user.email "your_email@youremail.com"
```

To verify that things are working properly, enter these commands and verify whether the output matches your name and email address.

```sh
git config --get user.name
```

```sh
git config --get user.email
```

GitHub recently changed the default branch on new repositories from master to main. Change the default branch for Git using this command:

```sh
git config --global init.defaultBranch main
```

Run these three commands to tell git to ignore .DS_Store files and .vscode folder:

```sh
echo .DS_Store >> ~/.gitignore_global
```

```sh
echo .vscode/ >> ~/.gitignore_global
```

```sh
git config --global core.excludesfile ~/.gitignore_global
```

## SSH Key

To create a new SSH key, run the following command inside your terminal. The -C flag followed by your email address ensures that GitHub knows who you are.

```sh
ssh-keygen -t ed25519 -C "your@email.com"
```

When it prompts you for a location to save the generated key, just push Enter.
Next, it will ask you for a password; enter one if you wish, but it’s not required.

Now you need to copy your public SSH key. To do this, we’re going to use a command called `cat` to read the file to the console (Note that the `.pub` file extension is important in this case).

```sh
cat ~/.ssh/id_ed25519.pub
```

Highlight and copy the output, which starts with ssh-ed25519 and ends with your email address.

Now, go into your GitHub settings > `SSH and GPG keys`. Click `New SSH Key`. Name your key something that is descriptive enough for you to remember where it came from and paste the content of your public key here.

Test the SSH connection by following the instructions [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection).

# Visual Studio Code

Get **Visual Studio Code** from their [website](https://code.visualstudio.com/).

`Shift` + `Cmd` + `P` to open the Command Palette and select `Shell Command: Install 'code' command in PATH`.

Go to `System Settings` > `Desktop & Dock` > `Windows` and set `Prefer tabs when opening documents` to `Always` so that native tabs work correctly.

## Extensions

### Utility

- [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)
- [Todo Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)
- [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

### Visual

- [Tokyo Night](https://marketplace.visualstudio.com/items?itemName=enkia.tokyo-night)
- [file-icons](https://marketplace.visualstudio.com/items?itemName=file-icons.file-icons)

## Settings

```
{
  "editor.fontFamily": "'Monaspace Neon', monospace",
  "editor.formatOnSave": true,
  "editor.wordWrap": "on",
  "workbench.editor.enablePreview": false,
  "editor.minimap.enabled": false,
  "workbench.startupEditor": "none",
  "editor.formatOnPaste": true,
  "editor.linkedEditing": true,
  "files.autoSave": "onFocusChange",
  "window.restoreWindows": "none",
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "explorer.autoReveal": false,
  "window.nativeTabs": true,
  "editor.stickyScroll.enabled": true,
  "editor.renderWhitespace": "boundary",
  "editor.smoothScrolling": true,
  "editor.cursorSmoothCaretAnimation": "on",
  "editor.guides.bracketPairs": "active",
  "workbench.iconTheme": "file-icons",
  "workbench.colorTheme": "Tokyo Night Storm"
}
```

# Node.js

Let's grab nvm:

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

Restart your terminal.

Test your nvm installation by running:

```sh
nvm --version
```

Now that we have nvm installed, we can install Node.

```sh
nvm install --lts
```

This will install the most recent stable version of Node in ‘long-term support’ (LTS).

We need to tell nvm which version of Node to use when we run the node command. It’s easy; just run the following command:

```sh
nvm use --lts
```

Now when you run `node -v`, you should see vXX.xx.x or something similar (with the X’s replaced with actual numbers).
