# Setting Up WSL and GitHub in WSL

## 1. Open PowerShell as Administrator
- Right-click on PowerShell and select **Run as administrator**.

## 2. Update WSL
- Type the following command in PowerShell:
  ```sh
  wsl --update
  ```
- Wait for the process to complete.

## 3. Set the Default User for Ubuntu to Root
- Run the following command in PowerShell:
  ```sh
  Ubuntu config --default-user root
  ```

## 4. Open Terminal and Select Ubuntu
- Install Zsh by running:
  ```sh
  apt install zsh -y
  ```

## 5. Install Oh My Zsh
- Run the following command:
  ```sh
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```

## 6. Install Zsh Plugins
- Install `zsh-autosuggestions`:
  ```sh
  git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
  ```
- Install `zsh-syntax-highlighting`:
  ```sh
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
  ```

## 7. Edit Zsh Configuration
- Open the Zsh configuration file:
  ```sh
  nano /root/.zshrc
  ```
- Press `Ctrl + W`, type `plugins`, and press `Enter`.
- Modify the plugins line to include:
  ```sh
  plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
  ```
- Save and exit by pressing `Ctrl + X`, then `Y`, and `Enter`.

## 8. Reload Zsh Configuration
- Apply the changes by running:
  ```sh
  source /root/.zshrc
  ```

## 9. Set Up SSH Key for GitHub
- Open your browser and log into your GitHub account.
- Go to **Settings** -> **SSH and GPG keys** -> **New SSH key**.
- Generate an SSH key in the Ubuntu terminal:
  ```sh
  ssh-keygen
  ```
- Press `Enter` for all prompts.
- Display the SSH key:
  ```sh
  cat /root/.ssh/id_rsa.pub
  ```
- Copy the output and add it to GitHub as a new SSH key.
