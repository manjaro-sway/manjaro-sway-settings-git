# Maintainer: Jonas Strassel <info@jonas-strassel.de>

pkgname=manjaro-sway-settings
pkgver=6.0.2
pkgrel=8
arch=('any')
_pkgbase=desktop-settings
url="https://github.com/Manjaro-Sway/$_pkgbase/"
license=('GPL')
pkgdesc='Manjaro Sway Settings'
groups=('sway-manjaro')
depends=(
    'manjaro-base-skel'
    'waybar' # configurable bar
    'light' # cli to control brightness
    'mako' # desktop notifications
    'sway' # the desktop manager
    'sbdp' # sway config docs parser
    'rofi-wayland' # launcher application
    'swaylock' # lockscreen
    'swayidle' # idle management daemon
    'grim' # screenshot tool
    'slurp' # helper for grim
    'wob' # wayland overlay bar for brightness and volume
    'wlogout' # nice logout menu
    'noto-fonts-emoji' # emoji font
    'foot' # terminal application
    'nerd-fonts-roboto-mono' # default monospace font
    'ttf-material-design-icons-webfont' # material design icons used in waybar
    'khal' # calendar application around caldav
    'lm_sensors' # display sensor information
    'manjaro-sway-wallpapers' # manjaro sway themed backgrounds
    'wf-recorder' # screen recording util
    'wl-clipboard' # copy/paste utilities for wayland
)
makedepends=('git')
optdepends=(
    'ranger: a keyboard centric file manager'
    'qutebrowser: a keyboard-centric browser'
    'flashfocus: better flashing on focus changes'
    'swaylock-effects: swaylock with nicer effects'
    'wlsunset: time & place based light temperature'
    'kanshi: automatically load matching output profiles'
    'autotiling: automated tiling'
    'sworkstyle: dynamic workspace names (icons) in waybar'
)
conflicts=('manjaro-desktop-settings' 'manjaro-sway-settings-git')
provides=('manjaro-desktop-settings')
source=("$pkgname-$pkgver.tar.gz::${url}/archive/${pkgver}.tar.gz")
_sourcemd5=fc9993bbacdcaab9321121fc67aee8d9
md5sums=("$_sourcemd5")
install=.install

package() {
    install -d $pkgdir/etc
    install -d $pkgdir/usr
    cp -r $_pkgbase-$pkgver/community/sway/etc/* "${pkgdir}/etc/"
    cp -r $_pkgbase-$pkgver/community/sway/usr/* "${pkgdir}/usr/" 
}
