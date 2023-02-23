# qBittorrent-nox Flatpak

<a href='https://flathub.org/apps/details/org.qbittorrent.qBittorrent-nox'><img width='240' alt='Get it on Flathub' src='https://flathub.org/api/badge?svg&locale=en'/></a>

## Installation

To install, simply click the above `Get it on Flathub` button and follow the instructions. \
In reality, 2 branches are provided:
1. Stable (default) \
   This follows the regular stable release of qBittorrent.
   * To install:
     ```shell
     flatpak install flathub org.qbittorrent.qBittorrent-nox
     ```
   * To run:
     ```shell
     flatpak run org.qbittorrent.qBittorrent-nox
     ```

2. Beta \
   This follows the latest development of qBittorrent and libtorrent-rasterbar. However, due to laziness
   it isn't updated regularly.
   * Add flathub-beta repository:
     ```shell
     flatpak remote-add flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
     ```
   * To install:
     ```shell
     flatpak install flathub-beta org.qbittorrent.qBittorrent-nox
     ```
   * To run:
     ```shell
     flatpak run org.qbittorrent.qBittorrent-nox//beta
     ```
   * Set stable version as the default when you invoke `flatpak run org.qbittorrent.qBittorrent-nox`
     ```shell
     sudo flatpak make-current org.qbittorrent.qBittorrent-nox stable
     ```
   * Set beta version as the default when you invoke `flatpak run org.qbittorrent.qBittorrent-nox`
     ```shell
     sudo flatpak make-current org.qbittorrent.qBittorrent-nox beta
     ```

## Revise Filesystem Permission
   In order to secure the installation, you are encouraged to remove the default `--filesystem=host` permission or reduce it to suit your need. \
   Ideally, `host` should not be the default but it cannot be changed now as it will massively disturb a lot of existing users and seeders. \
   To remove the permission, you can use [Flatseal](https://flathub.org/apps/com.github.tchx84.Flatseal) app or use the following command: `flatpak override --nofilesystem=host org.qbittorrent.qBittorrent-nox` \
   Note that there are various qBittorrent functionalities and use cases that would be easier to setup when `host` or some specific filesystem permission is granted.
   To name a few: Run external program on torrent complete. Migrate away from flatpak qBittorrent to non-flatpak qBittorrent. \
   Ref: https://docs.flatpak.org/en/latest/sandbox-permissions.html#filesystem-access

## Build Locally

1. Add flathub repository to current user:
   ```shell
   flatpak remote-add \
     --if-not-exists \
     --user \
     flathub https://dl.flathub.org/repo/flathub.flatpakrepo
   ```

2. Build it:
   ```shell
   flatpak-builder \
     --ccache \
     --force-clean \
     --install \
     --install-deps-from=flathub \
     --repo=repo \
     --sandbox \
     --user \
     _build \
     org.qbittorrent.qBittorrent-nox.yaml
   ```

3. Run it:
   ```shell
   flatpak run org.qbittorrent.qBittorrent-nox
   ```

4. Remove it:
   ```shell
   flatpak uninstall org.qbittorrent.qBittorrent-nox
   ```
