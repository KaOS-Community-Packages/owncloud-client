pkgname=owncloud-client
pkgver=1.7.80
_commit=fba9020
pkgrel=1
arch=('x86_64')
pkgdesc="Tool to synchronize files from ownCloud Server with your computer."
url="https://owncloud.org/"
license=('GPL2')
depends=('qt5-webkit' 'neon' 'qtkeychain')
makedepends=('cmake' 'python2-sphinx')
source=("https://github.com/owncloud/client/tarball/master/${pkgname}-${pkgver}.tar.gz")
md5sums=('0cd1b25fd135a3c7dfce297fca755b69')

build() {
  mkdir -p build
  cd build

  cmake ../${pkgname}-${_commit} \
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