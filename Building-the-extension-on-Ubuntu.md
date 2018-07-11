This guide has been tested on Ubuntu 18.04, with Bash.

## Preparing the Environment

The following commands can be used to prepare a new Ubuntu instance
for building the extension.

Open the console, install Git, Node.js, nvm and Yarn.

```shell
sudo apt-get update && sudo apt-get install -y build-essential git nodejs

wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
source ~/.bashrc

wget -qO- https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install -y yarn
```

Check the installed build dependencies.

```shell
git --version && node --version && nvm --version && yarn --version
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
yarn

# build for all supported browsers
yarn build:prod:zip:all

# build for a specific browser
# yarn build:prod:zip:chrome
# yarn build:prod:zip:firefox
# yarn build:prod:zip:opera
```

The extension will be in the `artifacts\<browser>` folder.
