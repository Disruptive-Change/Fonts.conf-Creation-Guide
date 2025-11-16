# **Universal Font Config**

A universal font configuration setup for **all Linux distributions**. This script allows you to easily apply custom font configurations for **Inter Variable**, **Ubuntu Nerd Font**, and **JetBrains Nerd Font**.

## **Features**

- Automatically sets up font configurations for **Inter Variable**, **Ubuntu Nerd Font**, and **JetBrains Nerd Font**.
- Compatible with **all Linux distros** using `fontconfig`.
- Can be used for both user-level and system-wide font configurations.
- Simple setup with just a single script.

## **Supported Fonts**

- **[Inter Variable](https://rsms.me/inter/)**: A versatile, modern sans-serif font designed for UI and readability.
- **[Ubuntu Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/tag/v2.1.0)**: The Ubuntu font with added support for various icons and symbols.
- **[JetBrains Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/tag/v2.1.0)**: A clean and modern font tailored for developers, with extensive icon support.

## **Installation** ##

#!/bin/bash

# Set the fontconfig directory to user's local config or system-wide config
FONTCONFIG_DIR="${HOME}/.config/fontconfig/conf.d"

# Check if we're running with root privileges for system-wide installation
if [ "$(id -u)" -eq 0 ]; then
    FONTCONFIG_DIR="/etc/fonts/conf.d"
fi

# Create the directory if it doesn't exist
mkdir -p "$FONTCONFIG_DIR"

# Define font configuration content for each font
INTER_FONT_CONFIG='<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
    <match target="pattern">
        <test qual="any" name="family">
            <string>Inter</string>
        </test>
        <edit name="family" mode="assign">
            <string>Inter</string>
        </edit>
        <edit name="weight" mode="assign">
            <double>400</double>
        </edit>
        <edit name="slant" mode="assign">
            <double>0</double>
        </edit>
        <edit name="width" mode="assign">
            <double>100</double>
        </edit>
        <edit name="hinting" mode="assign">
            <bool>true</bool> <!-- Corrected from string to bool -->
        </edit>
        <edit name="antialias" mode="assign">
            <bool>true</bool>
        </edit>
    </match>
</fontconfig>
'

UBUNTU_NERD_FONT_CONFIG='<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
    <match target="pattern">
        <test qual="any" name="family">
            <string>Ubuntu Nerd Font</string>
        </test>
        <edit name="family" mode="assign">
            <string>Ubuntu Nerd Font</string>
        </edit>
        <edit name="weight" mode="assign">
            <double>400</double>
        </edit>
        <edit name="slant" mode="assign">
            <double>0</double>
        </edit>
        <edit name="width" mode="assign">
            <double>100</double>
        </edit>
        <edit name="hinting" mode="assign">
            <bool>true</bool> <!-- Corrected from string to bool -->
        </edit>
        <edit name="antialias" mode="assign">
            <bool>true</bool>
        </edit>
    </match>
</fontconfig>
'

JETBRAINS_NERD_FONT_CONFIG='<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
    <match target="pattern">
        <test qual="any" name="family">
            <string>JetBrains Mono Nerd Font</string>
        </test>
        <edit name="family" mode="assign">
            <string>JetBrains Mono Nerd Font</string>
        </edit>
        <edit name="weight" mode="assign">
            <double>400</double>
        </edit>
        <edit name="slant" mode="assign">
            <double>0</double>
        </edit>
        <edit name="width" mode="assign">
            <double>100</double>
        </edit>
        <edit name="hinting" mode="assign">
            <bool>true</bool> <!-- Corrected from string to bool -->
        </edit>
        <edit name="antialias" mode="assign">
            <bool>true</bool>
        </edit>
    </match>
</fontconfig>
'

# Create the fonts.conf files for each font
echo "$INTER_FONT_CONFIG" > "$FONTCONFIG_DIR/00-inter-variable-fonts.conf"
echo "$UBUNTU_NERD_FONT_CONFIG" > "$FONTCONFIG_DIR/01-ubuntu-nerd-fonts.conf"
echo "$JETBRAINS_NERD_FONT_CONFIG" > "$FONTCONFIG_DIR/02-jetbrains-nerd-fonts.conf"

# Confirm installation
echo "Font configurations for Inter Variable, Ubuntu Nerd Font, and JetBrains Nerd Font have been set up successfully!"

# Optional: Reload fontconfig to apply changes
echo "Reloading fontconfig..."
fc-cache -f -v

# Done
echo "Font configuration setup complete!"

##################################################################################################################

Next Steps:

Copy this script into your setup-fonts.sh file.

Run the script: ./setup-fonts.sh

Rebuild the font cache (if needed): fc-cache -fv

Your Done.

