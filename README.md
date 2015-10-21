# Superlumic over Ansible - Automate our OSX installation and configuration

## Setup your environment to be Superlumic friendly

### Copy Cached installation items

  - Copy Xcode 7 to */tmp*
  - Setup Network environment by running
    ```bash
      sudo curl http://bnppfp2.ddns.net:9999/root/mac-os-dual-network/blob/master/update-ipconfig.sh?raw=true -o /etc/update-ipconfig.sh
    ```
    ```bash
      sudo chown root /etc/update-ipconfig.sh && sudo chmod +x /etc/update-ipconfig.sh && /etc/update-ipconfig.sh
    ```

### Install brew and Cask
```bash
  ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" && brew install caskroom/cask/brew-cask
```

## Run our superlumic rocket

```bash
  curl -s <PATH_TO_SUPERLUMIC_SCRIPT> | bash -s <PATH_TO_SUPERLUMIC_REPO> -u tester-ios|tester-android
```

## Fixes and features on the way

### Features
  - Install *XCode Commandline tool* from */tmp* if exists
  - Add *Network configuration script* in Superlumic script
  - Add *Oh-My-Zsh* in Superlumic script
  - Add brew and cask installation in Superlumic script
  - Add bookmarks in browsers
  - Cache Brew & Cask installation from */Library/Caches/Homebrew* & */Library/Caches/Homebrew/Casks*
  - Add tester-ios-and-android profile
  - Finish the build-server profile
  - Add devops-team profile

### Fixes
  - `sudo` not working for *Agreed Xcode License* task in */roles/profile-tester-ios/xcode.yml*
  - Update icons set instead of removing all icons before adding it.
  - Add icons at the end of the installation
  - Add brew cask cleanup at the end of the installation
