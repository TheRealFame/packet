# Maintainer: Fame <fame@famelinuxpc>
pkgname=packet
pkgver=0.7.3
pkgrel=1
pkgdesc="Quick Share client for Linux"
arch=('x86_64')
url="https://github.com/nozwock/packet"
license=('GPL3')
depends=('gtk4' 'libadwaita' 'dbus' 'protobuf')
makedepends=('meson' 'ninja' 'cargo' 'rust' 'blueprint-compiler' 'glib2' 'gettext' 'appstream' 'desktop-file-utils' 'pkgconf')
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/nozwock/packet/archive/v${pkgver}.tar.gz")
sha256sums=('SKIP')

prepare() {
  cd "${srcdir}/packet-${pkgver}"
}

build() {
  cd "${srcdir}/packet-${pkgver}"
  meson setup builddir --prefix=/usr --buildtype=release
  ninja -C builddir
}

package() {
  cd "${srcdir}/packet-${pkgver}"
  DESTDIR="${pkgdir}" ninja -C builddir install
}
