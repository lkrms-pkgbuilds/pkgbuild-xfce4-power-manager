# Maintainer: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=0.8.0
pkgrel=1
pkgdesc="power manager for xfce4 desktop"
arch=(i686 x86_64)
license=('GPL2')
url="http://xfce-goodies.berlios.de/"
groups=('xfce4-goodies')
depends=('xfce4-panel>=4.6.1' 'libnotify' 'hal' 'hicolor-icon-theme' 'librsvg')
makedepends=('pkgconfig' 'intltool')
options=('!libtool')
install=${pkgname}.install
source=(http://goodies.xfce.org/releases/${pkgname}/${pkgname}-${pkgver}.tar.bz2)
md5sums=('a73021d871607936409309186757dfb5')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./configure --prefix=/usr --sysconfdir=/etc --libexecdir=/usr/lib \
    --localstatedir=/var
  make || return 1
  make DESTDIR=${pkgdir} install || return 1
}
