# Defold Builder

A tiny Bash script for building, running and bundling Defold Games.
Originally developed by [@AstroChilli](https://github.com/astrochili) for using
Vscode with Defold, but has been extracted and hosted here for use with
other text editors too.

## Prerequisites

- Bob, the builder from the [Defold downloads page](https://d.defold.com)
- Dmengine from the [Defold downloads page](https://d.defold.com)

### Additional steps on Windows

- If you're running on Windows, you need to install Bash for Windows
- Download [x86_64-win32/defoldsdk.zip](https://d.defold.com/stable/) and
configure paths to `OpenAL32.dll` and `wrap_oal.dll` in `build.sh`.

After downloading the prerequisites, configure the path to bob.jar and dmengine
in `buid.sh`.

## Commands

The supported commands that you can execute are

- `./build.sh clean` : Cleans the build folder
- `./build.sh resolve` : Resolves all external library dependencies.
- `./build.sh build` : Builds the game for the current platform
- `./build.sh launch` : Launches the built game.
- `./build.sh bundle platform` : Bundles the game for the specified platform,
where platform is one of `Windows`, `Linux`, `macOS`, `Android`, `iOS` or `HTML5`.

## Fields

The script provides various fields that you can modify.

### General

- `bob_path` : The path to bob.jar
- `dummy_engine_path` : The path to the local download of dmengine. This version
is used to run Defold games without Native Extensions.
- `exclude` : The folders to be excluded from builds.

### Dependencies

- `email` : The email used to resolve dependencies
- `auth`  : Authentication token to resolve dependencies

### Bundle

- `texture_compression` : Whether texture compression should be used as
specified in texture profiles. Defaults to true.
- `with_symbols` : If the symbol file should be generated (if applicable).
Defaults to true.
- `liveupdate` : Whether liveupdate content should be published. Defaults to
false.

### iOS

- `mobileprovisioning` : Path to mobileprovisioning profile.
- `identity` : The name of your code signing identity from Keychain.

### Android

- `keystore` : The keystore to be used for signing the bundle
- `keystore_pass` : The password for the keystore used when signing the bundle.
- `bundle_format` : The format in which the apk should be bundled. Accepts either
`apk` or `aab`. Defaults to apk.
