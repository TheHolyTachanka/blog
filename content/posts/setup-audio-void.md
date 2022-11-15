+++
author = "TheHolyTachanka"
title = "Setting up audio on VoidLinux"
date = "2022-11-14"
description = "A guide on how to setup audio on VoidLinux"
tags = [
    "Void",
    "Linux",
    "Install guide",
    "No audio",
    "Audio fix"
]
+++

I recently installed void and experienced audio troubles; after a few of hours, I discovered a solution and wanted to share it here for future void users.(Thank you [MrRichBOB](https://www.reddit.com/user/MrRichBOB/) for finding a fix)

You must first add yourself to the audio group.
```sh
sudo usermod -aG audio <username>
```

After that, install the audio packages.
```sh
sudo xbps-install -Sy alsa-{utils,firmware,tools} apulse bluez{,-alsa} ffmpeg alsa-plugins{,-ffmpeg,-pulseaudio} pulseaudio pavucontrol
```

and finally, enable the alsa service
```sh
sudo ln -s /etc/sv/alsa /var/service/
```

then simply restart your system
```sh
sudo reboot
```