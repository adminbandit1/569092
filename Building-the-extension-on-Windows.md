This guide has been tested on Windows 10 Pro 64-bit, version 21H2,
with Command Prompt and PowerShell.

## Preparing the Environment

The build dependencies can be installed with winget, follow
[this](https://docs.microsoft.com/en-us/windows/package-manager/winget/)
guide to set it up. Alternatively, download and install
the listed dependencies from their official sources.

Open the console as the current user, install
Git and Node.js with winget.

```shell
winget install -e -s winget --id Git.Git --version 2.36.1
winget install -e -s winget --id OpenJS.NodeJS.LTS --version 16.15.0
```

Close and reopen the console as the current user,
check the installed build dependencies.

```shell
git --version && node --version
```

## Building the Extension

The build process consists of cloning the repository,
installing the dependencies, and building the extension.

Open the console as the current user,
build the extension for the intended browser.

```shell
# clone repository (replace <version>)
git clone --depth 1 --branch v<version> https://github.com/dessant/search-by-image.git
cd search-by-image

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