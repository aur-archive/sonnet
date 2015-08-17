# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=sonnet
pkgver=4.99.0
pkgrel=1
pkgdesc='Sonnet'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/sonnet'
license=('LGPL')
depends=('qt5-base' 'enchant')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('82aa19bbb80a4e6375e0066818694d95')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
