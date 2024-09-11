# 👋 Welcome to [NixOS](https://nixos.org/) 👋
This is a new experience, this system is not normal, like, **at all**, the system is decently stable, lets you replicate it with 1 or 2 files if something were to happen to it and in general, if you need to install more stuff you just need to add it to that 1 file unless is from a different package manager, I find it cool and you may too.
I've added the packages that you use and a bunch that you may need, the system is really barebones so you can modify it to your liking, remember to [ask me](https://furry.band/@moriyordle) if you need help with it.

Anyways, lets get to it

# Installation
  
  ⚠️ WARNING ⚠️ **Don't waste the Windows Drive, use a different SSD for this since you are first starting to use Linux for real, keep the Windows drive just in case, so don't format it, installing a new OS WILL DELETE your previous one if you are not careful**
  
 1. 💠 Booting NixOS
    - Download the system from NixOS' download [website](https://nixos.org/download/)
    - Use [Balena Etcher](https://etcher.balena.io/), [Rufus](https://rufus.ie/en/), or [Ventoy](https://www.ventoy.net/en/index.html) to make a bootable USB drive
    - Enter the 1 time boot menu (the key is different between motherboard makers, but normaly its F12) and select the newly flashed USB drive
 2. 💠 Installing NixOS
    - [Skip if you don't get the log in menu] If you see a prompt to enter a password, just hit enter, the live environment doesn't have a password so you'll be good to go
    - Once the system is booted, it'll launch the installation program called Calamares
    - Follow the instructions of the program, aside from the partitioning part of the installer, this ones are self explanatory so you'll be good on your own
    - Partitioning: I would suggest making a boot {/boot} (if using UEFI), a root {/}, a Home {/home} and a swap partition, the sizes may vary but the boot should be at least 512MB, the root I would recommend minimum 64GB, the swap 8GB should more than enough and the Home should get the rest of the drive's space
    - Keep following the instructions and let the program do its thing
   
  3. 🎉 YOU DID IT
     - After the program finishes the installation process, restart the PC
     - Let the PC boot into the system, it is recommended to unplug the USB Drive when rebooting the system
     - Log in to your system
     - Make it yours

After this steps, now you need to start adding the config file and the apps you need, I have everything in this repo so you won't have to do much aside from editing the configuration.nix file, running the flatpak commands we have bellow and theme it to your liking.

**HAVE FUN**

## ⚙️ configuration.nix ⚙️

This file is the entire system's configuration, some settings may vary from system to system, specially if you use a different boot loader, in the file I have attached is if you use GRUB, but the system may install Systemd-boot, if that's the case, keep the systemd-boot configuration and don't add the GRUB one
To change this you'll need to open the configuration.nix file on either nano, vim or Kate, this file is located under `/etc/nixos/`, there you'll find the `configuration.nix` file

- After you copy/edit the configuration.nix you have to reload the repos with this command
```
sudo nix-channel --update
```

- Then you have to rebuild the configuration with this one
```
sudo nixos-rebuild switch
```

⚠️ This last one has to be used everytime you modify the configuration.nix file, the first one can be used once a day or once a week, this is good for updating the system.

⚠️ For updating the system you have to do those 2 commands in that same order.

## 📦 Boxes 📦

🔍 The Boxes package is missing from the official repos, to install it you need to install it through [Flatpak](https://flatpak.org/), to do this after you edit the configuration.nix file to fit your pc and rebuild the system, you would need to input the following commands on Konsole

- This adds the [Flatpak](https://flatpak.org/) repos to the system, they are needed to install apps from [Flathub](https://flathub.org/)
```
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

- This installs [Boxes](https://gnomeboxes.org/), which is a hypervisor like [VirtualBox](https://www.virtualbox.org/) or [VMWare Player](https://www.vmware.com/products/desktop-hypervisor/workstation-and-fusion)
```
flatpak install flathub org.gnome.Boxes
```

🔄 Restart the system and the program should be installed. You only need to restart it once, after that what ever flatpak you install will appear in the app drawer 🔄
