# audio-services

This repository contains systemd unit files for Jack Audio and LinuxSampler And a2jmidi (Works with pulseaudio), allowing easy management and automation of these services on Linux systems . 

**Dependencies :**
- jack2
- jack2-dbus 
- a2jmidid
- linuxsampler
- pulseaudio-jack (For pulseaudio module jack)


**Usage :**

 Edit **dbus-org.jackaudio.service** this unit to change your sound card configuration .

**Note :** If you have LSCP files and you want to load it after  **Linuxsampler**  you need to edit ** ls-loader.service**  and set LSCP file path in your system.

Copy units files to path `~/.config/systemd/user/` if not exist create this path .

```bash
systemctl --user daemon-reload
systemctl --user enable  dbus-org.jackaudio.service
systemctl --user enable  dbus-org.a2jmidid.service
systemctl --user enable  linuxsampler.service
```

**Optional** (if you want load LSCP file) : 
```bash
systemctl --user enable  ls-loader.service
```
Reboot the system .
