## Universal Install

To install Tailscale on Linux with a single command, use this

	curl -fsSL https://tailscale.com/install.sh | sh

## Ubuntu 22.04 Install

Add the Tailscale signing key and repository

	curl -fsSL https://pkgs.tailscale.com/stable/ubuntu/jammy.noarmor.gpg | sudo tee /usr/share/keyrings/tailscale-archive-keyring.gpg >/dev/null
	curl -fsSL https://pkgs.tailscale.com/stable/ubuntu/jammy.tailscale-keyring.list | sudo tee /etc/apt/sources.list.d/tailscale.list

Then update the repositories

	sudo apt update

Install Tailscale

	sudo apt install tailscale

Then start up Tailscale

	sudo tailscale up

Navigate to the URL and authenticate with your Tailscale account to enable the device

You can list the Tailscale IPV4 address with

	tailscale ip -4

