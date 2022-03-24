# Truestamp Shortcuts

## About

This repository contains a collection of Truestamp utilities for the Apple [Shortcuts](https://support.apple.com/guide/shortcuts/welcome/ios) application for `iOS`, `iPadOS`, and `macOS`.

Some Truestamp shortcuts require an active Truestamp account, and an API Key. You can sign up for a free trial account at [www.truestamp.com](https://www.truestamp.com/). An API key can be generated from your account dashboard as needed.

## Requirements

These shortcuts have been tested on the following Apple platforms:

- macOS Monterey >= 12.3
- iPadOS >= 15.4
- iOS >= 15.4

Shortcuts are not supported on any other platforms.

## Setup

Per Apple security guidelines, you [must set a one time permission](https://support.apple.com/guide/shortcuts/adjust-privacy-settings-apd961a4fc65/5.0/ios/15.0) to allow any third-party scripts to be installed in the Shortcuts app.

Follow these simple steps for all of the platform(s) you plan to run Shortcuts on.

### macOS

Open `Shortcuts` application.

Go to `Shortcuts` > `Preferences...` menu

Turn on `Private Sharing`

We also recommend enabling `iCloud Sync` so that your Shortcuts are shared across devices.

### iPadOS

Go to `Settings` > `Shortcuts`.

Turn on `Private Sharing`.

We also recommend enabling `iCloud Sync` so that your Shortcuts are shared across devices.

### iOS

Go to `Settings` > `Shortcuts`.

Turn on `Private Sharing`.

We also recommend enabling `iCloud Sync` so that your Shortcuts are shared across devices.

## Installation

Once you have completed the previous setup steps for your platform(s) you can install our Shortcuts using the Apple provided iCloud sharing links below. When you click a link you'll be prompted to review some information about the Shortcut (and optionally view its code with the `...` button). After reviewing you can click on the `Add Shortcut` button to add it to your Shortcuts app.

[Install 'Submit to Truestamp' Shortcut](https://www.icloud.com/shortcuts/cb9487a2816e43dbb13a98d2cc8fd2ab)

[Install 'Get Observable Entropy' Shortcut](https://www.icloud.com/shortcuts/047d4dd807e64577bc27d1e6191feede)

## Usage

### Using the `Submit to Truestamp` Shortcut

This simple to use shortcut dramatically simplifies the process of submitting many forms of data to the Truestamp API. Additionally, it provides automatic archival storage of any submitted Items and the response Envelope provided by the API.

When you first install the Shortcut you will be prompted to set the following settings:

- `Truestamp API URL` : You should be able to select the default which is `https://api.truestamp.com/v1/items`.
- `Truestamp API Key` : This is your personal API key, which can be generated in your account dashboard at [https://www.truestamp.com/dashboard/keys](https://www.truestamp.com/dashboard/keys). It is suggested that you generate an API key that expires far in the future, or never expires.

On all platforms, multiple files can be selected and submitted in batches.

There are multiple ways of getting data into the Shortcut and sending it to Truestamp. The available forms of usage depend on the platform you are running the Shortcut on. Here are some examples:

#### on iOS / iPadOS

- By selecting file(s) in the `Files` application, or within most apps where [Share Sheets](https://developer.apple.com/design/human-interface-guidelines/ios/extensions/sharing-and-actions/) are available. Choose the `Share` > `Submit to Truestamp` menu item and your item will automatically be submitted. This process should be familiar if you know how to share a photo using the messages app for example.
- By opening the Shortcuts application and tapping the `Submit to Truestamp` icon and following the prompt to create some new content (e.g. take a photo), or choose some existing content to submit.

#### on macOS

- By selecting file(s) in finder, or anywhere that `Quick Actions` are available, and right clicking and choosing the `Quick Actions` > `Submit to Truestamp` menu item.
- By clicking the `Shortcuts` menu bar icon (if shown), clicking `Submit to Truestamp` and following the prompt to choose a file to share.
- By clicking the `Submit to Truestamp` icon within the Shortcuts application and following the prompts to create or choose some content to submit.

More advanced users or developers can also:

- Send data from another Shortcut to the `Submit to Truestamp` shortcut.
- Run a Shortcut from the [command line](https://support.apple.com/guide/shortcuts-mac/run-shortcuts-from-the-command-line-apd455c82f02/mac).

Command line example:

```sh
shortcuts run "Submit to Truestamp" -i ./my-important-data.txt
```

#### Archival Storage

On all platforms the API response `Envelope` and a copy of the original content you submitted to Truestamp, will be stored in the `Shortcuts` > `Truestamp` folder in `iCloud Drive`. You can find this folder by navigating in the `Files` app on iOS or iPadOS, or within the `Finder` on macOS. All original content will be hashed with the SHA-256 hash function and stored under its Truestamp ID as the base of the filename. For example, submitting a file called `hello.txt` will result in the storage of files with names like:

```txt
truestamp_test_01FYW11EKKG48SQ0NEYY813K05_1648060578996000-hello.txt
truestamp_test_01FYW11EKKG48SQ0NEYY813K05_1648060578996000.json
```

### Using the `Get Observable Entropy` Shortcut

This shortcut makes an API call to the [Observable Entropy](https://github.com/truestamp/observable-entropy/blob/main/README.md) project. This provides incontestable and verifiable public randomness. A `SHA-256` hash representing the latest entropy value will be returned by the shortcut.

If prompted to allow permissions to connect to `entropy.truestamp.com` you should choose to `Always Allow`.

This shortcut requires no additional configuration or API keys to operate.

Alternatively, the latest entropy value is also available for real-time display at [observable-entropy.truestamp.com](https://observable-entropy.truestamp.com/).

## Updating Shortcuts

Installed Shortcuts __do not update automatically__ when newer versions are released. You can manually update any Shortcut by deleting the old one and re-installing a new version. The installation links above should always point to the latest versions.

## Development

This repository also contains a copy of each shortcut as a file. The files are exported by first single-click selecting them in the Shortcuts application on macOS and then using the `File` > `Export` menu to save the export to the `src` directory in this repository.

Shortcut installation links are created by opening the shortcut in the editor, followed by the share button and `Copy iCloud Link`. The link(s) should be updated in the `Installation` section of this README.md file.

## Legal

Any software and content provided or linked to here is for the sole use, or review, by Truestamp customers on their own devices. Reproduction or use, in whole, or in part, by others is forbidden.

Copyright © 2020-2022 Truestamp, Inc. All rights reserved.
