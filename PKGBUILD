license=('GPL')
arch=('x86_64')
pkgname=printer-driver-brlaser
pkgver=4
pkgrel=1
pkgdesc="OpenSource cups driver for brother printer models"
depends=('cups' 'ghostscript')
makedepends=('cmake')
url="https://github.com/pdewacht/brlaser"
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/pdewacht/brlaser/archive/v${pkgver}.tar.gz")
md5sums=('58af90dea156d285a8a29ce4bbf9d5bd')

build() {
  mkdir -p build
  cd build

  cmake ../brlaser-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd build

  make DESTDIR=${pkgdir} install
}
