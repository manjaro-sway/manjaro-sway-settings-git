# Maintainer: Jonas Strassel <info@jonas-strassel.de>

pkgname=manjaro-sway-settings-git
pkgver=r2143.fed9b04a
pkgrel=1
arch=('any')
_pkgbase=desktop-settings
url="https://github.com/Manjaro-Sway/$_pkgbase"
license=('GPL')
pkgdesc='Manjaro Sway Settings'
groups=('sway-manjaro')
depends=(
    'manjaro-base-skel'
    'waybar'            # configurable bar
    'brightnessctl'     # cli to control brightness
    'mako'              # desktop notifications
    'sway'              # window manager
    'rofi-wayland'      # launcher application
    'gtklock'           # lockscreen
    'sway-services'     # systemd services for sway
    'wl-clip-persist'   # persists clipboard content between containers
    'swayidle'          # idle management daemon
    'grim'              # screenshot tool
    'slurp'             # helper for grim
    'wob'               # wayland overlay bar for brightness and volume
    'foot'              # terminal application
    'foot-terminfo'     # terminal info for foot
    'jq'                # json parsing and manipulation
    'calcurse'          # tui calendar application
    'lm_sensors'        # display sensor information
    'wf-recorder'       # screen recording util
    'wl-clipboard'      # copy/paste utilities for wayland
    'nwg-wrapper'       # conky like onscreen information'
    'noto-fonts-emoji'  # emoji font (e.g. weather icons)
    'btop'              # system monitor
    'swappy'            # screenshot editing tool
    'grimshot'          # screenshot tool
    'inotify-tools'     # file watchers etc
    'bluetuith'         # bluetooth management tool
    'swayr'             # lru window switcher for sway
    'bc'                # basic tiny calculation util
    'xdg-terminal-exec' # upcoming execute in terminal xdg standard
    'idlehack'          # inhibit swayidle on dbus messages that request screensaver inhibit
    'dex'               # executes desktop entries on autostart
    'swaybg'            # wallpaper setter
    'rofimoji'          # emoji picker
    'wtype'             # programmatically type
    ## theme
    'kvantum'                 # theme engine for qt
    'kvantum-qt5'             # theme engine for qt (qt 5 support)
    'ttf-jetbrains-mono-nerd' # default monospace font
    'ttf-roboto'              # default font
    'papirus-maia-icon-theme' # default icon theme
    'xcursor-breeze'          # default cursor theme
    'matcha-gtk-theme'        # default gtk (gnome etc.) theme
    'kvantum-theme-matcha'    # default kvantum (kde etc.) theme
)
makedepends=('git')
optdepends=(
    'qutebrowser: a keyboard-centric browser'
    'flashfocus: better flashing on focus changes'
    'waylock: reference lockscreen for ext-session-lock-v1'
    'gtklock: lockscreen based on gtkgreet'
    'swaylock: minimalistic lockscreen'
    'swaylock-effects: minimalistic lockscreen with fancy effects'
    'wlsunset: time & place based light temperature'
    'way-displays: automated display management'
    'autotiling: automated tiling'
    'sworkstyle: dynamic workspace names (icons) in waybar'
    'nwg-wrapper: conky like onscreen information'
    'cliphist: clipboard manager'
    'swaycwd: open here helper'
    'zeit: a simple time tracker'
    'dex: execute DesktopEntry files on autostart'
    'poweralertd: battery and power notifications'
    'wluma: adaptive brightness based on screen contents and ALS'
    'valent: kdeconnect-like tool without the kde bloat'
    'pacseek: package manager tui'
    'openbsd-netcat: network utility (e.g. for termbin)'
    'pacman-log-orphans-hook: pacman hook to log orphaned packages'
)
conflicts=('manjaro-sway-settings-git')
provides=('manjaro-desktop-settings')
source=(
    "$_pkgbase::git+${url}.git#branch=feat/light-dark-toggle"
    "https://github.com/arcolinux/arcolinux-on-the-road/raw/cfbcc902b9520cc4ff73584dd80f34c54a158c75/root/usr/local/bin/skel"
)
md5sums=(
    "SKIP"                             # desktop settings
    "3ce84d692c6fdbaf31e1b602bc890aa4" # skel update script from arcolinux
)
install=.install

pkgver() {
    cd $_pkgbase || exit
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
    install -d "$pkgdir"/etc
    install -d "$pkgdir"/usr/bin
    cp -r $_pkgbase/community/sway/etc/* "${pkgdir}/etc/"
    cp -r $_pkgbase/community/sway/usr/* "${pkgdir}/usr/"
    install -D -m 755 skel "${pkgdir}/usr/bin/skel"
}
