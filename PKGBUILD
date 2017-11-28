# $Id$
# Maintainer: Antonio Rojas <arojas@archlinux.org>

pkgname=kscreenlocker
pkgver=5.11.4
pkgrel=2
pkgdesc='Library and components for secure lock screen architecture'
arch=(x86_64)
url='https://www.kde.org/workspaces/plasmadesktop/'
license=(LGPL)
groups=(plasma)
depends=(kidletime kwayland kdeclarative)
makedepends=(extra-cmake-modules python kdoctools kcmutils libxcursor)
<<<<<<< HEAD
source=("https://download.kde.org/stable/plasma/$pkgver/$pkgname-$pkgver.tar.xz"{,.sig})
sha256sums=('87e049ea0771a72e2919fb618348c58f56b476d520f57ce7c269e877341a4464'
            'SKIP')
validpgpkeys=('2D1D5B0588357787DE9EE225EC94D18F7F05997E'  # Jonathan Riddell
              '348C8651206633FD983A8FC4DEACEA00075E1D76'  # KDE Neon
              'D07BD8662C56CB291B316EB2F5675605C74E02CF')  # David Edmundson
              

=======
source=("https://download.kde.org/stable/plasma/$pkgver/$pkgname-$pkgver.tar.xz")
sha256sums=('5ba019d5d002511ec09deb941af1c38b1373b7eac418853f98badbffa7621d44')
validpgpkeys=('2D1D5B0588357787DE9EE225EC94D18F7F05997E'  # Jonathan Riddell
              '348C8651206633FD983A8FC4DEACEA00075E1D76'  # KDE Neon
              'D07BD8662C56CB291B316EB2F5675605C74E02CF' # David Edmundson
			  '6DD4217456569BA711566AC7F06E8FDE7B45DAAC' # Eric Vidal
			  '5FF0C09152A95D743BFD60A402FD193357C6A9B6') # Herve VIDAL 
>>>>>>> e31ca28f591f4d6221a1ad9bd78e6c8d689e4d3d
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
