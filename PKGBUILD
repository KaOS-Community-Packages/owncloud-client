pkgname=owncloud-client
pkgver=2.11.1
pkgrel=1
arch=('x86_64')
pkgdesc="Tool to synchronize files from ownCloud Server with your computer."
url="https://owncloud.org/"
license=('GPL2')
depends=('qtwebengine' 'qtkeychain' 'qt5-base' 'sqlite')
makedepends=('cmake' )
source=("https://github.com/owncloud/client/archive/v${pkgver}.tar.gz")
md5sums=('ef30f98eb7092fa5dfad7e819ba26f0f')

build() {
    mkdir -p build
    cd build

    cmake ../client-${pkgver} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/usr
    make
}

package() {
    cd build
    make DESTDIR=${pkgdir} install
    rm -rf ${pkgdir}/usr/share/*-python
}
