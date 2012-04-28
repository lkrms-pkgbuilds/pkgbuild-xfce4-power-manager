# Maintainer: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=1.2.0
pkgrel=1
pkgdesc="Power manager for Xfce desktop"
arch=('i686' 'x86_64')
url="http://xfce-goodies.berlios.de/"
license=('GPL2')
groups=('xfce4-goodies')
depends=('xfce4-panel' 'upower' 'udisks' 'libnotify' 'hicolor-icon-theme')
makedepends=('pkgconfig' 'intltool')
options=('!libtool')
install=$pkgname.install
source=(http://archive.xfce.org/src/apps/$pkgname/1.2/$pkgname-$pkgver.tar.bz2)
sha256sums=('d7fb98a540284b62f4201527de17d4b24123f9d26c9f49131dd497c8387184e9')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  ./configure \
    --prefix=/usr \
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
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
