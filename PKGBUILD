# Maintainer: Joey Shi <root@joeyshi.xyz>
pkgname=dwl-wake
pkgver=0.9
pkgrel=7
pkgdesc="dwl with the ipc, ipc zoom, movestack and rounded corner patches and my config.h"
arch=('x86_64')
url="https://github.com/joeyshi12/dwl"
license=('GPL-3.0-or-later')
depends=('wlroots0.20' 'scenefx' 'libinput' 'libxkbcommon' 'wayland' 'libxcb' 'xcb-util-wm')
makedepends=('wayland-protocols' 'pkgconf')
optdepends=('xorg-xwayland: run X11 programs')
options=('!debug')  # no dwl-wake-debug package
provides=('dwl')
conflicts=('dwl')

# Builds the working tree this PKGBUILD is in, including uncommitted changes to config.h and colors.h
build() {
	cd "$startdir"
	make clean
	make
}

package() {
	cd "$startdir"
	make PREFIX=/usr DESTDIR="$pkgdir" install
}
