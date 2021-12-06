# Useful services

Certain services need to open on startup - use:

```sh
$ systemctl enable <service>
```

to do this. To get currently enabled services use:

```sh
$ systemctl list-unit-files | grep enabled
```

Notable services to enable on startup:

* `ntpd.service` - [Time synchronisation](https://wiki.archlinux.org/index.php/Network_Time_Protocol_daemon#Start_ntpd_at_boot)
* `snapd.socket` - Daemon to interact with [snap](https://wiki.archlinux.org/index.php/Snap) - snaps packages up common software tools (i.e. Skype) for easy Linux deployments (don't use much due to AUR).
* `dhcpcd.service` - DHCP client, needed for internet connectivity.
* `iwd.service` - WiFi daemon interacted with using `iwctl`
* `bluetooth.service`  - Bluetooth daemon, interacted with using `blutetoothctl`.

## Terminal

Using termite - see [here](https://github.com/jamiegl/config-dot/blob/main/termite/config) for colour scheme. Opacity requires picom.

## Window Manager

Using i3 ([gaps](https://github.com/Airblader/i3)) tiling window manager. Config file can be found [here](https://github.com/jamiegl/config-dot/blob/main/i3/config). Launched using `.xinitrc` - see [here](https://github.com/jamiegl/config-dot/blob/main/X/.xinitrc).

## Picom

Picom is a compositor (not sure what that is though) - allows for extra visual functionality such as opacity and shadows. Have this in i3 dotfile to launch it -

```
exec --no-startup-id picom -b
```

## Audio

Need [Pulseaudio](https://archlinux.org/packages/extra/x86_64/pulseaudio/) and [alsa-utils](https://archlinux.org/packages/extra/x86_64/alsa-utils/) is handy for `alsamixer`. Fixes for no audio - 

* Check if daemon is running
  
  ```sh
  $ pulseaudio --check -v 
  # If response says 'Daemon not running' then start
  $ pulseaudio --start
  ```

* Restart Pulseaudio daemon
  
  ```sh
  $ pulseaudio -k
  $ pulseaudio --start
  ```

* Check default sink and set to correct
  
  ```sh
  $ pacmd list-sinks
  # set desired device (using the index) as default
  $ pacmd set-default-sink <index-of-sink>
  ```
  
  ## Screenshots
  
  Using [maim](https://archlinux.org/packages/community/x86_64/maim/). Keybinds defined in i3 config file - 
  
  ```shell
  bindsym $mod+shift+s exec maim -s | xclip -selection clipboard -t image/png
  ```
