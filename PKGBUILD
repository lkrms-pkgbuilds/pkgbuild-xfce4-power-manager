# Maintainer: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=1.4.2
pkgrel=1
pkgdesc="Power manager for Xfce desktop"
arch=('i686' 'x86_64')
url="http://www.xfce.org/"
license=('GPL2')
groups=('xfce4')
depends=('upower' 'libnotify' 'hicolor-icon-theme')
optdepends=('xfce4-panel: for the Xfce panel plugin'
            'lxpanel: for the LXDE panel plugin')
makedepends=('intltool' 'xfce4-panel' 'lxpanel')
install=$pkgname.install
source=(http://archive.xfce.org/src/apps/$pkgname/1.4/$pkgname-$pkgver.tar.bz2)
sha256sums=('f28bad9270a155566e5ccf03de91c9cce7516e28192f3c0259a620bbce9d6b97')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  ./configure \
    --prefix=/usr \
    --sysconfdir=/etc \
    --sbindir=/usr/bin \
    --libexecdir=/usr/lib \
    --localstatedir=/var \
    --disable-network-manager \
    --enable-polkit \
    --disable-debug
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
