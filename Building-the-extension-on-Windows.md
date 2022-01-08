This guide has been tested on Windows 10 Pro 64-bit, version 21H1,
with Command Prompt and PowerShell.

## Preparing the Environment

The build dependencies can be installed with Chocolatey, follow
[this](https://chocolatey.org/install) guide to set it up.
Alternatively, download and install the listed dependencies
from their official sources.

Open the console as an administrator, install
Git and Node.js with Chocolatey.

```shell
choco install git -y --version 2.32.0.2
choco install nodejs-lts -y --version 12.22.8
```

Open the console as the current user, check the installed build dependencies.

```shell
git --version && node --version
```

## Building the Extension

The build process consists of cloning the repository,
installing the dependencies, and building the extension.

Open the console as the current user,
build the extension for the intended browsers.

```shell
# clone repository (replace <version>)
git clone --depth 1 --branch v<version> https://github.com/dessant/search-by-image.git
cd search-by-image

# install dependencies
npm install

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