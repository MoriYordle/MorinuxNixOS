# Configuration of Morinux for NixOS

![Welcome to Morinux](https://github.com/MoriYordle/MorinuxNixOS/blob/main/logo.png)

- Cloning and copying configuration.nix
```
git clone https://github.com/MoriYordle/MorinuxNixOS.git
sudo cp ~/MorinuxNixOS/configuration.nix /etc/nixos/
```
- Update Nix channel and build the new configuration
```
sudo nixos-channel --update
sudo nixos-rebuild switch
```
