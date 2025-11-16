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

## **Installation**

### **1. Clone the repository:**

```bash
git clone https://github.com/<your-username>/universal-font-config.git
cd universal-font-config

2. Make the script executable:

chmod +x setup-fonts.sh

3. Run the script:

For user-level configuration (local only):

./setup-fonts.sh

For system-wide configuration (requires root privileges):

sudo ./setup-fonts.sh

The script will:

    Install font configuration files for the specified fonts.

    Place the configuration files in the appropriate directory (~/.config/fontconfig/conf.d/ for user, or /etc/fonts/conf.d/ for system-wide).

    Reload the font cache using fc-cache to apply changes.

How It Works

    The script creates fonts.conf files for Inter Variable, Ubuntu Nerd Font, and JetBrains Nerd Font with settings for weight, slant, hinting, and anti-aliasing.

    It checks if the script is run with root privileges and installs the font configurations either system-wide or locally.

Requirements

    fontconfig (installed by default on most distros).

    Basic shell environment (bash).

Troubleshooting

If the fonts are not being applied:

    Run fc-cache -f -v manually to force a font cache rebuild.

    Make sure the fonts are installed on your system. If not, download them using the links above.

Contributing

Feel free to fork the repository, open issues, or submit pull requests. If you find any bugs or need additional font support, please open an issue!
License

This project is licensed under the MIT License.
