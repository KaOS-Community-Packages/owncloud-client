pkgname=owncloud-client
pkgver=2.1.81
_pkgver=2.2.0-beta2
pkgrel=1
arch=('x86_64')
pkgdesc="Tool to synchronize files from ownCloud Server with your computer."
url="https://owncloud.org/"
license=('GPL2')
depends=('qt5-webkit' 'neon' 'qtkeychain' 'qt5-base' 'sqlite')
makedepends=('cmake' )
source=("https://github.com/owncloud/client/archive/v${_pkgver}.tar.gz")
md5sums=('bfc6629fdf43cb160a98948abce9792f')

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
