# Maintainer: Simon Büeler <simon.bueeler@icloud.com>

_pkgbase=desktop-settings
pkgname=manjaro-sway-settings
pkgver=20201220
pkgrel=1
arch=('any')
url="https://gitlab.manjaro.org/profiles-and-settings/$_pkgbase"
_branch=sway
license=('GPL')
pkgdesc='Manjaro Linux sway settings'
groups=('sway-manjaro')
depends=('waybar'
        'swaylock'
        'wofi'
        'swayidle'
        'pamixer'
        'playerctl'
        'light'
        'grim'
        'mako'
        'gnome-keyring'
        'blueberry'
        'manjaro-base-skel')
makedepends=('git')
optdepends=('gedit: the default text editor'
        'sterminal: the default terminal'
        'vim: the default cli text editor'
        'spacefm: the default file manager'
        'gtk-theme-breath: the default gtk theme'
        'breeze-maia-icon-themes: the default icon theme')
conflicts=('manjaro-desktop-settings')
provides=('manjaro-desktop-settings')
source=("git+$url.git#branch=$_branch")
sha256sums=('SKIP')

pkgver() {
    date +%Y%m%d
}

package() {
    cd $_pkgbase
    install -d $pkgdir/etc
    cp -r community/sway/skel $pkgdir/etc
    install -d $pkgdir/usr/share/glib-2.0/schemas
    cp community/sway/schemas/* $pkgdir/usr/share/glib-2.0/schemas
}
