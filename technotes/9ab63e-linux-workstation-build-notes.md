---
id: "b06f0f"
---
--- 
id: "9ab63e" 
title: "Linux Workstation Build Notes" 
type: "note" 
tags: [tech, linux, workstation, dotfiles] 
date: "2025-11-20" 
---

# Linux Workstation Build Notes

## Linux With BTRFS, Encryption, and Swap


- This blog post will demonstrate how I set up a new Arch Linux install with
  BTRFS, an encrypted filesystem with dm-crypt, encrypted swap partition via a
  swap file, and (optionally) hibernation.
  [link](https://www.codyhou.com/arch-encrypt-swap/)

- Omarchy installer repository. This is a great reference for how customisation
  can be done and how to integrate different [[tui-tools]] into a working
  environment. [link](https://github.com/basecamp/omarchy) 

- 

## Portable Linux

References for installing a portable Linux on a usb stick.

- Install Arch Linux on a USB: Your Ultimate Portable OS Setup [link](https://sysguides.com/install-arch-linux-on-a-usb)

## Deployment

- Amazing `Makefile` to deploy and configure dotfiles+environment.
  [link](https://github.com/masasam/dotfiles/blob/cf5a28654bf546509184176958773eb843e7f3fb/Makefile)

## Tools

### Virtualisation

#### KVM

- Properly Install KVM on Linux. [link](https://sysguides.com/install-kvm-on-linux)

## Security

### Yubikey

- Using PIV for SSH through PKCS #11.
  [link](https://developers.yubico.com/PIV/Guides/SSH_with_PIV_and_PKCS11.html)

- Yubikey PIV Howto
  [link](http://cedric.dufour.name/blah/IT/YubiKeyHowto.html)

- Yubikey PIV Slots Overview
  [link](https://developers.yubico.com/PIV/Introduction/Certificate_slots.html)

- 

### GPG Password Store

- How to change the gpg key of the pass password store
  [link](https://askubuntu.com/questions/929307/how-to-change-the-gpg-key-of-the-pass-password-store)
  Use `pass init [-p path] <gpg-id>` where `<gpg-id>` specifies the new gpg key 
  with which you want to encrypt your passwords. According to the pass man page.



## References

[tui-tools]: technotes/707b9a-tui-tools.md
[nvim-config]: technotes/
