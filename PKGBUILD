pkgname=owncloud-client
pkgver=2.1.0
_pkgver=2.1.0
pkgrel=1
arch=('x86_64')
pkgdesc="Tool to synchronize files from ownCloud Server with your computer."
url="https://owncloud.org/"
license=('GPL2')
depends=('qt5-webkit' 'neon' 'qtkeychain')
makedepends=('cmake' 'python2-sphinx')
source=("https://github.com/owncloud/client/archive/v${_pkgver}.tar.gz")
md5sums=('5618f6a6ebb85b503c6321f41ff61934')

build() {
  mkdir -p build
  cd build

  cmake ../client-${_pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_INSTALL_LIBDIR=lib \
    -DCMAKE_INSTALL_SYSCONFDIR=/etc/${pkgname}
  make
}

package() {
  cd build

  make DESTDIR=${pkgdir} install
}
