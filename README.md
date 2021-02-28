# BPMN file editor for Nextcloud

![Static analysis](https://github.com/Loydl/nc-bpm-app/workflows/Static%20analysis/badge.svg)
![PHP Tests](https://github.com/Loydl/nc-bpm-app/workflows/PHP%20Tests/badge.svg)
![Lint](https://github.com/Loydl/nc-bpm-app/workflows/Lint/badge.svg)
![Downloads](https://img.shields.io/github/downloads/Loydl/nc-bpm-app/total.svg)
![GitHub release](https://img.shields.io/github/release/Loydl/nc-bpm-app.svg)

This app integrates the [BPMN.io editor](https://bpmn.io) into [Nextcloud](https://nextcloud.com).

![Screenshot editor](https://raw.githubusercontent.com/Loydl/nc-bpm-app/master/docs/screenshot-editor.png)

## :heart_eyes: Features
This integration provides the following features:

* **Editor** Edit BPMN diagrams on every folder with write permission
* **Viewer** View BPMN diagrams if you have no write permission
* **New diagrams** Create new diagrams via the Nextcloud files app

## :rocket: Install it
The easiest way to install this app is by using the [Nextcloud app store](https://apps.nextcloud.com/apps/files_bpm).
If you like to build from source, please continue reading.

To install it change into your Nextcloud's apps directory:

    cd nextcloud/apps

Then run:

    git clone https://github.com/Loydl/nc-bpm-app.git files_bpm

Then install the dependencies using:

    yarn install && composer install

Last thing you have to do is to build all assets with:

    yarn build

## :nerd_face: Release guide
This repo contains some Node scripts to simplify the release process on Linux
systems. They require openssl and gpg installed on your system and assume that
you have a valid [signing key] in `~/.nextcloud/certificates/files_bpm.key`.
Make sure that gpg and git is configured properly to use your default signing
key.

1. bump version in `package.json`
2. run `node scripts/build-release.js --stable` (for nightlies omit `--stable`)
3. `node scripts/publish-release.js` will generate a changelog from your
   commits, create and sign a release commit, and upload your app to Github and
   the Nextcloud app store

[signing key]: https://docs.nextcloud.com/server/stable/developer_manual/app_publishing_maintenance/code_signing.html
