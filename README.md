# bazzite-dx-nix &nbsp; [![build-ublue](https://github.com/footvaalvica/bazzite-dx-nix/actions/workflows/build.yml/badge.svg)](https://github.com/footvaalvica/bazzite-dx-nix/actions/workflows/build.yml)

This is a very barebones image just to add support for Nix to Bazzite, via creating an empty and persistent `/nix` directory.

## Desktop Environment
As with the other ublue-os images, this image comes with either KDE or GNOME Desktop Environment.
The images respect Bazzite naming convention:
- **bazzite-deck-nix**
- **bazzite-deck-gnome-nix**
- **bazzite-deck-nvidia-nix**
- **bazzite-deck-nvidia-gnome-nix**
- **bazzite-dx-nix**
- **bazzite-dx-gnome-nix**
- **bazzite-dx-nvidia-nix**
- **bazzite-dx-nvidia-gnome-nix**

## Installation

To rebase an existing atomic Fedora installation to the latest build:

- First choose the flavor of the image you'd like to install, in this case **bazzite-deck-nix**.

- Then rebase to the unsigned image, to get the proper signing keys and policies installed:
  ```
  rpm-ostree rebase ostree-unverified-registry:ghcr.io/footvaalvica/bazzite-deck-nix:latest
  ```
- Reboot to complete the rebase:
  ```
  systemctl reboot
  ```
- Then rebase to the signed image, like so:
  ```
  rpm-ostree rebase ostree-image-signed:docker://ghcr.io/footvaalvica/bazzite-deck-nix:latest
  ```
- Reboot again to complete the installation
  ```
  systemctl reboot
  ```

The `latest` tag will automatically point to the latest build.

## Verification

These images are signed with [Sigstore](https://www.sigstore.dev/)'s [cosign](https://github.com/sigstore/cosign). You can verify the signature by downloading the `cosign.pub` file from this repo and running the following command:

```bash
cosign verify --key cosign.pub ghcr.io/footvaalvica/bazzite-dx-nix
```

This README file was shamelessly copied from [Sparkrai's repo](https://github.com/Sparkrai/bazzite-dx/blob/main/README.md)
