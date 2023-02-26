# qBittorrent Flatpak
<a href='https://flathub.org/apps/details/org.qbittorrent.qBittorrent'><img width='240' alt='Download on Flathub' src='https://flathub.org/assets/badges/flathub-badge-en.svg'/></a>

## Installation
To install, simply click on the above 'Download on Flathub' button and follow the instructions. \
In reality, 2 branches are provided:
1. stable (default) \
   This follows the regular stable release of qBittorrent (with GUI).
   * To install:
     ```shell
     flatpak install flathub org.qbittorrent.qBittorrent
     ```
   * To run:
     ```shell
     flatpak run org.qbittorrent.qBittorrent
     ```

2. beta \
   This follows the latest development of qBittorrent and libtorrent-rasterbar. However, due to laziness
   it isn't updated regularly.
   * Add flathub-beta repository:
     ```shell
     flatpak remote-add flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
     ```
   * To install:
     ```shell
     flatpak install flathub-beta org.qbittorrent.qBittorrent
     ```
   * To run:
     ```shell
     flatpak run org.qbittorrent.qBittorrent//beta
     ```
   * Set stable version as the default when you invoke `flatpak run org.qbittorrent.qBittorrent`
     ```shell
     sudo flatpak make-current org.qbittorrent.qBittorrent stable
     ```
   * Set beta version as the default when you invoke `flatpak run org.qbittorrent.qBittorrent`
     ```shell
     sudo flatpak make-current org.qbittorrent.qBittorrent beta
     ```
