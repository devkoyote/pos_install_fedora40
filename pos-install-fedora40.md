# UPDATE SYSTEM 
$ sudo dnf upgrade --refresh

# RPM FUSION FREE
sudo dnf install http://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-40.noarch.rpm

# IMPORT KEY GPG
$ sudo rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-rpmfusion-free-fedora-40

# RPM NON FREE
$ sudo dnf install http://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-40.noarch.rpm

# IMPORT KEY GPG
$ sudo rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-rpmfusion-nonfree-fedora-40

# RPM TAINTED (FREE)
$ sudo dnf install rpmfusion-free-release-tainted

# RPM TAINTED NON-FREE
$ sudo dnf install rpmfusion-nonfree-release-tainted

# ENABLE FLATHUB
$ flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo

# INSTALL CODECS
$ sudo dnf swap ffmpeg-free ffmpeg --allowerasing

$ sudo dnf groupupdate multimedia --setop="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin

$ sudo dnf groupupdate sound-and-video

$ sudo dnf install amrnb amrwb faad2 flac gpac-libs lame libde265 libfc14audiodecoder mencoder x264 x265

# ACTIVATED HARDWARE GPU (OPTIONAL - AMD)
$ sudo dnf swap mesa-va-drivers mesa-va-drivers-freeworld
$ sudo dnf swap mesa-vdpau-drivers mesa-vdpau-drivers-freeworld

# STEAM OR OTHERS (LIBRARIES I686 - AMD)
$ sudo dnf swap mesa-va-drivers.i686 mesa-va-drivers-freeworld.i686
$ sudo dnf swap mesa-vdpau-drivers.i686 mesa-vdpau-drivers-freeworld.i686

# INSTALL VLC
$ sudo dnf install vlc

# INSTALL AUDACITY
$ sudo dnf install audacity

# INSTALL KDENLIVE
$ sudo dnf install kdenlive

# INSTALL OBS STUDIO
$ sudo dnf install obs-studio

# INSTALL DISCORD
$ sudo dnf install discord

# INSTALL TELEGRAM_DESKTOP
$ sudo dnf install telegram-desktop

# INSTALL GOOGLE_CHROME
$ sudo dnf install 'https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm'

# OPEN-JDK OTHER VERSIONS
$ sudo dnf install java-1.8.0-openjdk
$ sudo dnf install java-11-openjdk
$ sudo dnf install java-17-openjdk
$ sudo dnf install java-20-openjdk

# INSTALL STEAM ( AMD )
$ sudo dnf install mesa-dri-drivers.i686 mesa-libGL.i686 xorg-x11-drv-amdgpu
$ sudo dnf install steam

# DECOMPRESSORS
$ sudo dnf install cabextract lzip p7zip p7zip-plugins unrar

# TEAMVIEWER
$ sudo dnf install https://download.teamviewer.com/download/linux/teamviewer.x86_64.rpm

# DOCKER

$ sudo dnf install dnf-plugins-core

$ sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo

$ sudo dnf install docker-ce docker-ce-cli containerd.io

$ sudo systemctl start docker

$ sudo docker run hello-world

$ sudo systemctl enable docker

$ sudo groupadd docker && sudo gpasswd -a {$USER} docker && sudo systemctl restart docker

$ newgrp docker
