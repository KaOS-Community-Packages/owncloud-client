pkgname=owncloud-client
pkgver=1.7.1
_pkgver=1.7.1-qt54
pkgrel=1
arch=('x86_64')
pkgdesc="Tool to synchronize files from ownCloud Server with your computer."
url="https://owncloud.org/"
license=('GPL2')
depends=('qt5-webkit' 'neon' 'qtkeychain')
makedepends=('cmake' 'python2-sphinx')
source=("https://github.com/owncloud/client/archive/v${_pkgver}.tar.gz")
md5sums=('a3cc2ca86dbf8c34b5057a8ee4540bdb')

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