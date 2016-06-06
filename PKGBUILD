pkgname=owncloud-client
pkgver=2.2.1
pkgrel=1
arch=('x86_64')
pkgdesc="Tool to synchronize files from ownCloud Server with your computer."
url="https://owncloud.org/"
license=('GPL2')
depends=('qt5-webkit' 'neon' 'qtkeychain' 'qt5-base' 'sqlite')
makedepends=('cmake' )
source=("https://github.com/owncloud/client/archive/v${pkgver}.tar.gz")
md5sums=('4144ba59266df7843dada5b3f463cc1e')

build() {
  mkdir -p build
  cd build

  cmake ../client-${pkgver} \
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
