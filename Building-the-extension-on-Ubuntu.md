This guide has been tested on Ubuntu 22.04, with Bash.

## Preparing the Environment

The following commands can be used to prepare a new Ubuntu instance
for building the extension.

Open the console, install Git and nvm.

```shell
sudo apt update && sudo apt install -y build-essential git

wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
source ~/.bashrc
```

Check the installed build dependencies.

```shell
git --version && nvm --version
```

## Building the Extension

The build process consists of cloning the repository,
installing the dependencies, and building the extension.

Open the console, build the extension for the intended browsers.

```shell
# clone repository (replace <version>)
git clone --depth 1 --branch v<version> https://github.com/dessant/search-by-image.git
cd search-by-image

# install Node.js
nvm install

# install dependencies
npm install --legacy-peer-deps

# build for Chrome
npm run build:prod:zip:chrome

# build for Edge
npm run build:prod:zip:edge

# build for Firefox
npm run build:prod:zip:firefox

# build for Opera
npm run build:prod:zip:opera
```

The extension will be in the `artifacts\<browser>` folder.