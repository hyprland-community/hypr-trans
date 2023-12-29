# hypr-trans

[![ShellCheck](https://github.com/jlaunay/hypr-trans/actions/workflows/shellcheck.yml/badge.svg)](https://github.com/jlaunay/hypr-trans/actions/workflows/shellcheck.yml)

hypr-trans is a tiny bash utility that sets alpha attribute of an Hyprland window.

## Installation

1. Using AUR package [hypr-trans-git](https://aur.archlinux.org/packages/hypr-trans-git)
2. Manually by using `make PREFIX=/usr`

## Dependencies

   - hyprctl
   - jq

## Usage
### Command line
```sh
Usage: hypr-trans [plus|minus]

  plus    Increase current Window ALPHA value
  minus   Decrease current Window ALPHA value

 `hypr-trans init` must be executed once before `plus` or `minus`.
 ```

 ### Hyprland keybind
 You can configure a key binding to exec `hypr-trans`, see [Hyprland wiki](https://wiki.hyprland.org/Configuring/Binds/) for more information.

 Below is an excerpt from the Hyprland config file using `SUPER + SHIFT` key and mouse wheel `up/down` as binding.
```jsonc
# Bind mouse wheel scroll to adjust opacity (alpha) - see binds.scroll_event_delay
exec-once=hypr-trans init
bind = SUPERSHIFT, mouse_up, exec, hypr-trans plus
bind = SUPERSHIFT, mouse_down, exec, hypr-trans minus
```

Using mouse_down/mouse_up you may wish to adjust the reset time, see `scroll_event_delay` [here](https://wiki.hyprland.org/Configuring/Variables/#binds).

Setting `scroll_event_delay` to 30ms.
```jsonc
binds {
    scroll_event_delay = 30
}
```

