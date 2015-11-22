pkgname=owncloud-client
pkgver=2.0.2
_pkgver=2.0.2
pkgrel=1
arch=('x86_64')
pkgdesc="Tool to synchronize files from ownCloud Server with your computer."
url="https://owncloud.org/"
license=('GPL2')
depends=('qt5-webkit' 'neon' 'qtkeychain')
makedepends=('cmake' 'python2-sphinx')
source=("https://github.com/owncloud/client/archive/v${_pkgver}.tar.gz")
md5sums=('fb445c0c068b3f7fb428465b14295d5e')

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
