# $Id: PKGBUILD 217037 2014-07-18 11:07:46Z lcarlier $
# Maintainer: Andreas Radke <andyrtr@archlinux.org>
# Contributor: Gerardo Exequiel Pozzi <vmlinuz386@yahoo.com.ar>

pkgname=xf86-video-modesetting
pkgver=0.9.0
pkgrel=2
pkgdesc="X.org generic modesetting video driver"
arch=('i686' 'x86_64')
url="http://xorg.freedesktop.org/"
license=('custom')
depends=('libdrm>=2.4.37' 'systemd')
makedepends=('xorg-server-devel' 'X-ABI-VIDEODRV_VERSION=18')
conflicts=('xorg-server<1.16' 'X-ABI-VIDEODRV_VERSION<18' 'X-ABI-VIDEODRV_VERSION>=19')
groups=('xorg-drivers' 'xorg')
groups=('xorg-drivers' 'xorg')
source=(${url}/releases/individual/driver/${pkgname}-${pkgver}.tar.bz2)
sha256sums=('90cf085573203dfadd48ea69bd694c4d04ccbe088b6855e9c85c34bb8a95d75c')

build() {
  cd ${pkgname}-${pkgver}
  ./configure --prefix=/usr
  make
}

package() {
  cd ${pkgname}-${pkgver}
  make DESTDIR="${pkgdir}" install
  install -m755 -d "${pkgdir}/usr/share/licenses/${pkgname}"
  install -m644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/"
}
