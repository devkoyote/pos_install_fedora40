Here’s a standardized version of your MD, organized and formatted for clarity:

---

# System Update and Installation Guide

## Update System
```bash
$ sudo dnf upgrade --refresh
```

## RPM Fusion Free
```bash
$ sudo dnf install http://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-40.noarch.rpm
```

### Import GPG Key
```bash
$ sudo rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-rpmfusion-free-fedora-40
```

## RPM Non-Free
```bash
$ sudo dnf install http://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-40.noarch.rpm
```

### Import GPG Key
```bash
$ sudo rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-rpmfusion-nonfree-fedora-40
```

## RPM Tainted (Free)
```bash
$ sudo dnf install rpmfusion-free-release-tainted
```

## RPM Tainted Non-Free
```bash
$ sudo dnf install rpmfusion-nonfree-release-tainted
```

## Enable Flathub
```bash
$ flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

## Install Codecs
```bash
$ sudo dnf swap ffmpeg-free ffmpeg --allowerasing
$ sudo dnf groupupdate multimedia --setop="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin
$ sudo dnf groupupdate sound-and-video
$ sudo dnf install amrnb amrwb faad2 flac gpac-libs lame libde265 libfc14audiodecoder mencoder x264 x265
```

## Activate Hardware GPU (Optional - AMD)
```bash
$ sudo dnf swap mesa-va-drivers mesa-va-drivers-freeworld
$ sudo dnf swap mesa-vdpau-drivers mesa-vdpau-drivers-freeworld
```

## Install Libraries for Steam and Others (i686 - AMD)
```bash
$ sudo dnf swap mesa-va-drivers.i686 mesa-va-drivers-freeworld.i686
$ sudo dnf swap mesa-vdpau-drivers.i686 mesa-vdpau-drivers-freeworld.i686
```

## Install Applications
### VLC
```bash
$ sudo dnf install vlc
```
### Audacity
```bash
$ sudo dnf install audacity
```
### Kdenlive
```bash
$ sudo dnf install kdenlive
```
### OBS Studio
```bash
$ sudo dnf install obs-studio
```
### Discord
```bash
$ sudo dnf install discord
```
### Telegram Desktop
```bash
$ sudo dnf install telegram-desktop
```
### Google Chrome
```bash
$ sudo dnf install 'https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm'
```

## OpenJDK Other Versions
```bash
$ sudo dnf install java-1.8.0-openjdk
$ sudo dnf install java-11-openjdk
$ sudo dnf install java-17-openjdk
$ sudo dnf install java-20-openjdk
```

## Install Steam (AMD)
```bash
$ sudo dnf install mesa-dri-drivers.i686 mesa-libGL.i686 xorg-x11-drv-amdgpu
$ sudo dnf install steam
```

## Install Decompressors
```bash
$ sudo dnf install cabextract lzip p7zip p7zip-plugins unrar
```

## Install TeamViewer
```bash
$ sudo dnf install https://download.teamviewer.com/download/linux/teamviewer.x86_64.rpm
```

## Install Docker
```bash
$ sudo dnf install dnf-plugins-core
$ sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
$ sudo dnf install docker-ce docker-ce-cli containerd.io
$ sudo systemctl start docker
$ sudo docker run hello-world
$ sudo systemctl enable docker
$ sudo groupadd docker && sudo gpasswd -a $USER docker && sudo systemctl restart docker
$ newgrp docker
```

---

Feel free to adjust any sections or let me know if you need more modifications!
