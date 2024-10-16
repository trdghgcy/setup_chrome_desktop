#!/bin/bash

# Update packages and install XFCE and XRDP
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install -y xfce4 xfce4-terminal xrdp

# Install Google Chrome
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
sudo apt-get install -f -y  # Fix any dependency issues

# Configure XRDP to use XFCE
echo "xfce4-session" > ~/.xsession
sudo systemctl enable xrdp
sudo systemctl restart xrdp

# Allow XRDP through the firewall
sudo ufw allow 3389/tcp

# Clean up
rm google-chrome-stable_current_amd64.deb

echo "Setup complete! You can connect via RDP to your server."
