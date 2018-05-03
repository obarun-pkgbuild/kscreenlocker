pkgname=kscreenlocker
pkgver=5.12.5
pkgrel=2
pkgdesc='Library and components for secure lock screen architecture'
arch=(x86_64)
url='https://github.com/KDE/kscreenlocker'
license=(LGPL)
groups=(plasma)
depends=(kidletime kwayland kdeclarative)
makedepends=(extra-cmake-modules kdoctools kcmutils libxcursor)
source=("https://download.kde.org/stable/plasma/$pkgver/$pkgname-$pkgver.tar.xz")
sha256sums=('b86d1d725212b5250dada0f7d69a34e52d0170940177703e82a365b89d9d8822')
validpgpkeys=('2D1D5B0588357787DE9EE225EC94D18F7F05997E'  # Jonathan Riddell
              '0AAC775BB6437A8D9AF7A3ACFE0784117FBCE11D'  # Bhushan Shah <bshah@kde.org>
              'D07BD8662C56CB291B316EB2F5675605C74E02CF'  # David Edmundson
              '1FA881591C26B276D7A5518EEAAF29B42A678C20'  # Marco Martin <notmart@gmail.com>
			  '5FF0C09152A95D743BFD60A402FD193357C6A9B6')  # Herve VIDAL

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../$pkgname-$pkgver \
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

