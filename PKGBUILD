# Maintainer: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=1.2.0.198.g76d1f4f
pkgrel=1
pkgdesc="Power manager for Xfce desktop"
arch=('i686' 'x86_64')
url="http://www.xfce.org/"
license=('GPL2')
groups=('xfce4')
depends=('xfce4-panel' 'upower' 'udisks' 'libnotify' 'hicolor-icon-theme')
makedepends=('intltool' 'xfce4-dev-tools' 'git')
install=$pkgname.install
source=(git://git.xfce.org/xfce/xfce4-power-manager)
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/$pkgname"

  git describe --long | sed 's/^xfce4-power-manager-//;s/-/./g'
}

build() {
  cd "$srcdir/$pkgname"

  ./autogen.sh \
    --prefix=/usr \
    --sysconfdir=/etc \
    --sbindir=/usr/bin \
    --libexecdir=/usr/lib \
    --localstatedir=/var \
    --disable-network-manager \
    --enable-polkit \
    --enable-dpms \
    --disable-debug
  make
}

package() {
  cd "$srcdir/$pkgname"
  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
