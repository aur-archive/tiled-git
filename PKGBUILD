# Maintainer: RevenantX <doomrevx[at]gmail[dot]com>
pkgname=tiled-git
pkgver=v0.12.3.r27.g4b64473
pkgrel=1
pkgdesc='A general purpose tile map editor, built to be flexible and easy to use'
arch=('i686' 'x86_64')
url='http://mapeditor.org'
license=('GPL')
depends=('qt5-base' 'libgl' 'gtk-update-icon-cache')
makedepends=('mesa' 'qt5-tools' 'git')
conflicts=('tiled')
replaces=('tiled')
install=${pkgname}.install
source=("git+https://github.com/bjorn/tiled.git")
md5sums=('SKIP')

pkgver() {
  cd "${srcdir}/tiled"
  git describe --long --tags | sed -r 's/([^-]*-g)/r\1/;s/-/./g'
}

build() {
  cd "$srcdir/tiled"
  qmake -r INSTALL_HEADERS=yes RPATH=no PREFIX=/usr
  make
}

package() {
  cd tiled
  make install INSTALL_ROOT=$pkgdir
}

