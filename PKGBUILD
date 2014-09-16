# Maintainer: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=1.4.0
pkgrel=2
pkgdesc="Power manager for Xfce desktop"
arch=('i686' 'x86_64')
url="http://www.xfce.org/"
license=('GPL2')
groups=('xfce4')
depends=('xfce4-panel' 'upower' 'libnotify' 'hicolor-icon-theme')
makedepends=('intltool')
install=$pkgname.install
source=(http://archive.xfce.org/src/apps/$pkgname/1.4/$pkgname-$pkgver.tar.bz2
        fix-handle-lid-switch.patch)
sha256sums=('3fba9d1bdb2f535e5a5c2a832503368d26629d6fe496c547fa93a3278d2cf6e7'
            '18ff68052e7a3ab3df920bed1b3add4e8f22dd99a05cdf3b50e5cac45e4c719c')

prepare() {
  cd "$srcdir/$pkgname-$pkgver"

  # https://bugzilla.xfce.org/show_bug.cgi?id=11160
  patch -Np1 -i ../fix-handle-lid-switch.patch
}

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
