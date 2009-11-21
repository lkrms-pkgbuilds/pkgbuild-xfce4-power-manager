# Maintainer: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=0.8.4.2
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
source=(http://archive.xfce.org/src/apps//${pkgname}/0.8/${pkgname}-${pkgver}.tar.bz2)
md5sums=('3131257750766838a64a9bb7f74eb2a1')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./configure --prefix=/usr --sysconfdir=/etc --libexecdir=/usr/lib \
    --localstatedir=/var
  make || return 1
  make DESTDIR=${pkgdir} install || return 1
}
