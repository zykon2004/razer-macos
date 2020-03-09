# razer-macos

Open source color effects manager for Razer peripherals on macOS. First of its kind available on the latest macOS (10.15 Catalina).

All keyboards supported by the [openrazer](http://openrazer.github.io) project should work. 

Official drivers (Synapse 2) supports only up to macOS 10.14 Mojave. Currently, there are no plans by Razer to support macOS with the new Synapse 3.
See [source](https://support.razer.com/articles/1543762911).

## Usage

Ensure xcode command line tools are installed,

Install node package dependencies:

    yarn

Build drivers:

    node-gyp configure build

Run development server:

    yarn dev

Build dmg:

    yarn dist

## Implementation

Drivers are ported from the [openrazer](https://github.com/openrazer/openrazer) project for Linux.
The goal is to support all devices from openrazer on macOS.

An Electron macOS menu bar app is used for the front-end. 
The C driver is exposed as a native Node.js addon using node-addon-api, which gets called by Electron.

## Device support

Currently only Razer keyboard support has been added.

Tested working for:

* Razer Huntsman

Adding new peripherals types should be relatively simple. See [wiki](https://github.com/1kc/razer-macos/wiki).

## TODO

* Pack src/assets with webpack for the production build
* Finish adding different colour effects
* Add node-gyp to package.json scripts

## Credits

Builds on work done by these projects:

* [openrazer](https://github.com/openrazer/openrazer)
* [osx-razer-blade](https://github.com/kprinssu/osx-razer-blade)
* [osx-razer-led](https://github.com/dylanparker/osx-razer-led)
