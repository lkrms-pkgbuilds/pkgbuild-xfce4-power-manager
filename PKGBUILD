# Maintainer: Evangelos Foutras <evangelos@foutrelis.com>
# Contributor: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=1.0.11
pkgrel=2
pkgdesc="Power manager for Xfce desktop"
arch=('i686' 'x86_64')
url="http://xfce-goodies.berlios.de/"
license=('GPL2')
groups=('xfce4-goodies')
depends=('xfce4-panel' 'upower' 'udisks' 'libnotify' 'hicolor-icon-theme'
         'librsvg')
makedepends=('pkgconfig' 'intltool')
options=('!libtool')
install=$pkgname.install
source=(http://archive.xfce.org/src/apps/$pkgname/1.0/$pkgname-$pkgver.tar.bz2
        fix-french-translation.patch)
sha256sums=('cfa85d839458fa2e9c2ee874d7d64ab00a95d6d51e6acf0ac082ffc700fe4339'
            'acae23105905f13d65eafac2a7a03b2f15a1b143e7606ef077ace30497f6c448')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  # Fix crashes caused by the French .po file
  # https://bugs.archlinux.org/task/29294
  patch -Np1 -i "$srcdir/fix-french-translation.patch"

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
