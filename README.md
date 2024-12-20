# hyprland-watcher-window

A script which connects to the active [Hyprland](https://github.com/hyprwm/Hyprland) socket and saves which window is currently focused. This is a wayland version of [this](https://github.com/purarue/aw-watcher-window) CLI tool.

This works much nicer than the X11 version since it no longer has to poll the active window, and receives events over the socket whenever Hyprland broadcast any changes.

This saves when the window was initially focused, how long it was focused for, the app name and window title, as provided by Hyprland.

```bash
Usage: hyprland-active-window [OPTIONS]

Options:
  -d, --datafile TEXT      File to write data to  [required]
  -i, --ignore-regex TEXT  Regex to ignore when writing to file
  --help                   Show this message and exit.
```

## Install

```
pip install git+https://purarue/hyprland-active-window
```

## Example

```
hyprland-active-window -d ~/Documents/focused_window.csv
```

Like `window_watcher`, this CSV can be parsed with [active_window](https://github.com/purarue/active_window) to python, or into JSON. This is also used internally in [HPI](https://github.com/purarue/HPI/blob/master/my/activitywatch/active_window.py)
