# $Id$
# Maintainer: Antonio Rojas <arojas@archlinux.org>

pkgname=kscreenlocker
pkgver=5.11.3
pkgrel=2
pkgdesc='Library and components for secure lock screen architecture'
arch=(x86_64)
url='https://www.kde.org/workspaces/plasmadesktop/'
license=(LGPL)
groups=(plasma)
depends=(kidletime kwayland kdeclarative)
makedepends=(extra-cmake-modules python kdoctools kcmutils libxcursor)
source=("https://download.kde.org/stable/plasma/$pkgver/$pkgname-$pkgver.tar.xz")
sha256sums=('5ba019d5d002511ec09deb941af1c38b1373b7eac418853f98badbffa7621d44')
validpgpkeys=('2D1D5B0588357787DE9EE225EC94D18F7F05997E'  # Jonathan Riddell
              '348C8651206633FD983A8FC4DEACEA00075E1D76'  # KDE Neon
              'D07BD8662C56CB291B316EB2F5675605C74E02CF' # David Edmundson
			  '6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal
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
