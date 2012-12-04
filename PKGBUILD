# Maintainer: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=1.2.0
pkgrel=3
pkgdesc="Power manager for Xfce desktop"
arch=('i686' 'x86_64')
url="http://www.xfce.org/"
license=('GPL2')
groups=('xfce4')
depends=('xfce4-panel' 'upower' 'udisks' 'libnotify' 'hicolor-icon-theme')
makedepends=('pkgconfig' 'intltool')
options=('!libtool')
install=$pkgname.install
source=(http://archive.xfce.org/src/apps/$pkgname/1.2/$pkgname-$pkgver.tar.bz2
        xfce4-power-manager-1.2.0-sync-en-gb-translation.patch)
sha256sums=('d7fb98a540284b62f4201527de17d4b24123f9d26c9f49131dd497c8387184e9'
            'c8e1dfafd685c2abf1fcc2b3682f5b1eb2e7f1d4fa557f11a7478437eef9a933')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  # Fix en_GB translation
  # https://bugs.archlinux.org/task/30055
  patch -d po -Np0 -i \
    "$srcdir/xfce4-power-manager-1.2.0-sync-en-gb-translation.patch"

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
