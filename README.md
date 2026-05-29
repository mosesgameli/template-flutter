# Flutter Android Codespaces Template

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/mosesgameli/template-flutter?quickstart=1)

This repository is a GitHub Codespaces template for Flutter development with Android command line tools installed in the dev container image.

The Codespace uses a prebuilt container image from GitHub Container Registry so first startup pulls an image instead of building Flutter and the Android SDK from scratch.

## What's Included

- Flutter from the latest `stable` channel
- Android command line tools `14742923`
- Android SDK platform API `36`
- Android build-tools `37.0.0`
- OpenJDK 17
- VS Code Flutter and Dart extensions
- Codespaces machine request: 4 cores, 16 GB RAM, 32 GB storage
- Prebuilt `linux/amd64` dev container image: `ghcr.io/mosesgameli/template-flutter:latest`

## Startup And Architecture

This template targets the standard x64 Codespaces machine for the requested 4-core, 16 GB RAM, 32 GB storage setup. The dev container image is built for `linux/amd64` by GitHub Actions on an x64 Ubuntu runner.

Building locally and copying SDK folders into Codespaces is not recommended. A macOS build contains host-specific binaries and paths, and Apple Silicon machines default to ARM images unless you force the target platform. If you need to build the image locally, build and push the Linux x64 image instead:

```sh
docker buildx build --platform linux/amd64 --push -t ghcr.io/mosesgameli/template-flutter:latest -f .devcontainer/Dockerfile .devcontainer
```

Use a separate `linux/arm64` image only after verifying Flutter, Android command line tools, and platform tools work correctly on ARM Linux.

## Use This Template

Create a new Codespace from this template:

```text
https://codespaces.new/mosesgameli/template-flutter?quickstart=1
```

Or use the GitHub **Use this template** button to create a new repository, then create a Codespace from that repository.

## Verify The Environment

The template does not run `flutter doctor` automatically so Codespaces can finish startup as soon as the prebuilt image is ready. Run it manually inside the Codespace when you want to verify the toolchain:

```sh
flutter doctor -v
```

You can run it whenever you need to check the Flutter and Android setup.