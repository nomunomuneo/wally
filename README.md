# Wally

This script is a simple curses-based utility designed to browse and set wallpapers on Unix-like systems.

## Features

- **Curses-based Interface**: Provides a terminal-based file browser to select wallpapers.
- **Configurable**: Uses a TOML configuration file to store settings such as the wallpaper command.
- **File Browsing**: Navigate through directories to select the desired wallpaper.
- **Supported Formats**: Automatically detects and allows setting of wallpapers in various image formats (e.g., .png, .jpg).

## Requirements

- Python 3.x
- `curses` library (usually comes pre-installed with Python)
- `toml` library (`pip install toml` if not installed)
- Linux based OS

## Usage

### Installation

1. Clone the repository or download the script.
2. Ensure Python and required libraries are installed.
3. Optionally, configure `config.toml` with your preferred settings.

### Command-line Options

- `-f, --folder <FOLDER>`: Specify the starting folder for browsing wallpapers (default: current directory).
- `-c, --config <CONFIG_FILE>`: Specify the path to the TOML configuration file (default: `~/.config/wally/config.toml` or `config.toml` in the current directory).
- `-r, --restore`: Restore the last set wallpaper.

### Example Usage

```bash
wally -f ~/Pictures/Wallpapers -c /path/to/custom/config.toml
```

## Configuration File (config.toml)

The configuration file allows customization of the wallpaper setter behavior. Here's an example `config.toml` structure:

```toml
[wallpaper]
set_command = "feh --bg-scale {file}"  # Example command to set wallpaper using `feh`
restore_path = "/path/to/last/set/wallpaper.jpg"  # Optional: last set wallpaper path
```

## Notes

- Ensure your system has the necessary tools (`feh`, `swaybg`, etc.) installed for setting wallpapers based on your chosen `set_command`.
- This script assumes a Unix-like environment and may not work as expected on Windows.

## License

This script is licensed under the MIT License.