# $Id$
# Maintainer: Antonio Rojas <arojas@archlinux.org>

pkgname=kscreenlocker
pkgver=5.11.5
pkgrel=2
pkgdesc='Library and components for secure lock screen architecture'
arch=(x86_64)
url='https://www.kde.org/workspaces/plasmadesktop/'
license=(LGPL)
groups=(plasma)
depends=(kidletime kwayland kdeclarative)
makedepends=(extra-cmake-modules python kdoctools kcmutils libxcursor)
source=("https://download.kde.org/stable/plasma/$pkgver/$pkgname-$pkgver.tar.xz"{,.sig})
sha256sums=('5f59936eba34b57068d265d823e4525cb7ab7a81c8e7b954c8b6eeda25f22b63'
            'SKIP')
validpgpkeys=('5FF0C09152A95D743BFD60A402FD193357C6A9B6')  # Herve VIDAL

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../$pkgname-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_INSTALL_LIBDIR=lib \
    -DCMAKE_INSTALL_LIBEXECDIR=/usr/lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}
