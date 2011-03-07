# Maintainer: Andreas Radke <andyrtr@archlinux.org>
# Contributor: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=1.0.10
pkgrel=2
pkgdesc="power manager for xfce4 desktop"
arch=(i686 x86_64)
license=('GPL2')
url="http://xfce-goodies.berlios.de/"
groups=('xfce4-goodies')
depends=('xfce4-panel>=4.7.4' 'upower' 'udisks' 'libnotify>=0.7.1' 'hicolor-icon-theme' 'librsvg')
makedepends=('pkgconfig' 'intltool')
options=('!libtool')
install=${pkgname}.install
source=(http://archive.xfce.org/src/apps/${pkgname}/1.0/${pkgname}-${pkgver}.tar.bz2
	xfce4-power-manager-1.0.10-libnotify-0.7.patch)
md5sums=('38cbd272eb30e36ae538d9f38858bd38'
         'c790f973c29654701bb0748f842be4f7')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}

  patch -Np1 -i ${srcdir}/xfce4-power-manager-1.0.10-libnotify-0.7.patch
  
  ./configure --prefix=/usr \
	--sysconfdir=/etc \
	--libexecdir=/usr/lib \
	--localstatedir=/var \
	--disable-network-manager \
	--enable-polkit \
	--enable-dpms \
	--disable-debug
  make
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  make DESTDIR=${pkgdir} install
}
