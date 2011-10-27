# Maintainer: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=1.0.10
pkgrel=2
pkgdesc="Power manager for Xfce desktop"
arch=('i686' 'x86_64')
url="http://xfce-goodies.berlios.de/"
license=('GPL2')
groups=('xfce4-goodies')
depends=('xfce4-panel' 'upower' 'udisks' 'libnotify' 'hicolor-icon-theme' 'librsvg')
makedepends=('pkgconfig' 'intltool')
options=('!libtool')
install=$pkgname.install
source=(http://archive.xfce.org/src/apps/$pkgname/1.0/$pkgname-$pkgver.tar.bz2
        xfce4-power-manager-1.0.10-libnotify-0.7.patch)
sha1sums=('64dd7a8fae9cd1cbcf6403d2f51f2281f38cca05'
          'e93908a1f238d820d410d7fcb3ea54aa96be23c8')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  patch -Np1 -i "$srcdir/xfce4-power-manager-1.0.10-libnotify-0.7.patch"

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
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
