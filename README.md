# Configuration of Morinux for NixOS

# Cloning the repository to pull configuration.nix
1- git clone [this repo]

# Copy and paste the new configuration
2- sudo cp ~/MorinuxNixOS/configuration.nix /etc/nixos/

# Update Nix channel for up to date packages
3- sudo nixos-channel --update

# Build on system the new configuration
4- sudo nixos-rebuild switch
