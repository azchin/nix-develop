# Install Nix
```conf ~/.config/nix/nix.conf
experimental-features = nix-command flakes
```

```
usermod --append --groups nix-users USERNAME
systemctl enable --now nix-daemon
nix-channel --add https://nixos.org/channels/nixpkgs-unstable
nix-channel --update
```

# Install direnv and setup nix-direnv
The `.envrc` in current directory already sources nix-direnv.
```
echo "use flake" >> .envrc && direnv allow
```

# Start shell
```
nix develop
```

# Maintenance
```
nix flake update
nix-collect-garbage
```
