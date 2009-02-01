# Maintainer: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=0.6.0
pkgrel=1
pkgdesc="power manager for xfce4 desktop"
arch=(i686 x86_64)
license=('GPL2')
url="http://xfce-goodies.berlios.de/"
groups=('xfce4-goodies')
depends=('libxfcegui4>=4.5.99.1' 'libnotify' 'hal' 'hicolor-icon-theme' 'librsvg')
makedepends=('pkgconfig')
options=('!libtool')
install=${pkgname}.install
source=(http://goodies.xfce.org/releases/${pkgname}/${pkgname}-${pkgver}.tar.bz2)
md5sums=('c6740c9f4db0dece39ae7dace26c645b')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./configure --prefix=/usr --sysconfdir=/etc --libexecdir=/usr/lib \
    --localstatedir=/var --disable-static
  make || return 1
  make DESTDIR=${pkgdir} install
}
