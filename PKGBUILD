# Maintainer: GnaphronG <gnaphron(at)gmail(dot)com>

_pkgbase=mt7610u
pkgname=mt7610u-dkms
pkgver=1
pkgrel=1
pkgdesc="The kernel modules for mt7010u Wifi chip(DKMS)"
arch=('armv6h')
url="https://www.amazing.com/"
license=('GPL2')
depends=('dkms')
conflicts=("${_pkgbase}")
install=${pkgname}.install
source=("${_pkgbase}"::"git+https://github.com/GnaphronG/mt7610u.git"
        'dkms.conf')
md5sums=('SKIP' 'SKIP')

build() {
    msg2 "Build"
}

package() {
  # Install
  msg2 "Starting make install..."

  # Copy dkms.conf
  install -Dm644 dkms.conf "${pkgdir}"/usr/src/${_pkgbase}-${pkgver}/dkms.conf

  # Set name and version
  sed -e "s/@_PKGBASE@/${_pkgbase}/" \
      -e "s/@PKGVER@/${pkgver}/" \
      -i "${pkgdir}"/usr/src/${_pkgbase}-${pkgver}/dkms.conf

  # Copy sources (including Makefile)
  cp -r ${_pkgbase}/* "${pkgdir}"/usr/src/${_pkgbase}-${pkgver}/
}
