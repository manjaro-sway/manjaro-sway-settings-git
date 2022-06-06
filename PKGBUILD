# Maintainer: Jonas Strassel <info@jonas-strassel.de>

pkgname=manjaro-sway-settings-git
pkgver=11.1.1.r1.g88515e3e
pkgrel=4
arch=('any')
_pkgbase=desktop-settings
_branch=sway
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
    'foot-terminfo' # terminal info for foot
    'nerd-fonts-roboto-mono' # default monospace font
    'jq' # json parsing and manipulation
    'khal' # calendar application around caldav
    'lm_sensors' # display sensor information
    'manjaro-sway-wallpapers' # manjaro sway themed backgrounds
    'wf-recorder' # screen recording util
    'wl-clipboard' # copy/paste utilities for wayland
    'nwg-wrapper' # conky like onscreen information'
    'noto-fonts-emoji' # emoji font (e.g. weather icons)
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
    'swaycwd: open here helper'
    'zeit: a simple time tracker'
    'dex: execute DesktopEntry files on autostart'
    'poweralertd: battery and power notifications'
)
conflicts=('manjaro-desktop-settings' 'manjaro-sway-settings-git')
provides=('manjaro-desktop-settings')
source=("$_pkgbase-$pkgver::git+${url}.git#branch=${_branch}")
_sourcemd5=e089f0633fca6feb202183b4249e8e34
md5sums=("SKIP")
install=.install

pkgver() {
    cd $_pkgbase-$pkgver
    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
    install -d $pkgdir/etc
    install -d $pkgdir/usr
    cp -r $_pkgbase-$pkgver/community/sway/etc/* "${pkgdir}/etc/"
    cp -r $_pkgbase-$pkgver/community/sway/usr/* "${pkgdir}/usr/" 
}
