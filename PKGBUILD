# Maintainer: Jonas Strassel <info@jonas-strassel.de>

pkgname=manjaro-sway-settings-git
pkgver=9.1.0.r2.g679ae628
pkgrel=1
arch=('any')
_pkgbase=desktop-settings
_branch="sway"
url="https://github.com/Manjaro-Sway/$_pkgbase"
license=('GPL')
pkgdesc='Manjaro Sway Settings'
groups=('sway-manjaro')
depends=(
    'manjaro-base-skel'
    'waybar' # configurable bar
    'light' # cli to control brightness
    'mako' # desktop notifications
    'sway' # the desktop manager
    'rofi-wayland' # launcher application
    'swaylock' # lockscreen
    'swayidle' # idle management daemon
    'grim' # screenshot tool
    'slurp' # helper for grim
    'wob' # wayland overlay bar for brightness and volume
    'foot' # terminal application
    'nerd-fonts-roboto-mono' # default monospace font
    'jq' # json parsing and manipulation
    'khal' # calendar application around caldav
    'lm_sensors' # display sensor information
    'manjaro-sway-wallpapers' # manjaro sway themed backgrounds
    'wf-recorder' # screen recording util
    'wl-clipboard' # copy/paste utilities for wayland
    'noto-fonts-emoji' # emoji font (e.g. weather)
)
makedepends=('git')
optdepends=(
    'qutebrowser: a keyboard-centric browser'
    'flashfocus: better flashing on focus changes'
    'swaylock-effects: swaylock with nicer effects'
    'wlsunset: time & place based light temperature'
    'kanshi: automatically load matching output profiles'
    'autotiling: automated tiling'
    'sworkstyle: dynamic workspace names (icons) in waybar'
    'nwg-wrapper: conky like onscreen information'
    'cliphist: clipboard manager'
)
conflicts=('manjaro-desktop-settings')
provides=('manjaro-desktop-settings')
source=("${_pkgbase}::git+${url}.git#branch=${_branch}")
sha256sums=('SKIP')
install=.install

pkgver() {
    cd $_pkgbase
    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
    install -d $pkgdir/etc
    install -d $pkgdir/usr
    cp -r $_pkgbase/community/sway/etc/* "${pkgdir}/etc/"
    cp -r $_pkgbase/community/sway/usr/* "${pkgdir}/usr/"
}
