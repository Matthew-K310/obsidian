Created: 11032025

Type: [[mini]]

Tags: [[tailscale]], [[server]]
### Install package signing key and repository

curl -fsSL https://pkgs.tailscale.com/stable/ubuntu/jammy.noarmor.gpg | sudo tee /usr/share/keyrings/tailscale-archive-keyring.gpg >/dev/null
curl -fsSL https://pkgs.tailscale.com/stable/ubuntu/jammy.tailscale-keyring.list | sudo tee /etc/apt/sources.list.d/tailscale.list

### Install Tailscale

sudo apt update
sudo apt install tailscale

### Authenticate

sudo tailscale up

### Find Tailscale IPv4

tailscale ip -4
