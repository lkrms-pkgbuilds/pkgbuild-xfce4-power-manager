# Maintainer: Evangelos Foutras <foutrelis@archlinux.org>
# Maintainer: Robin Candau <antiz@archlinux.org>
# Contributor: Tobias Kieslich <tobias funnychar archlinux.org>

pkgname=xfce4-power-manager
pkgver=4.18.4
pkgrel=2
pkgdesc="Power Manager for Xfce"
arch=('x86_64')
url="https://docs.xfce.org/xfce/xfce4-power-manager/start"
license=('GPL-2.0-or-later')
groups=('xfce4')
depends=('libxfce4ui' 'upower' 'libnotify' 'xfce4-notifyd' 'hicolor-icon-theme')
makedepends=('git' 'glib2-devel' 'intltool' 'xfce4-dev-tools' 'xfce4-panel')
source=("git+https://gitlab.xfce.org/xfce/xfce4-power-manager.git#tag=$pkgname-$pkgver")
sha256sums=('bbd3b3f584ec8838132fbd79b3815563cf3d478ba3895f7118203d1c7039f0dc')

prepare() {
  cd $pkgname
  ./autogen.sh \
    --prefix=/usr \
    --sysconfdir=/etc \
    --sbindir=/usr/bin \
    --localstatedir=/var \
    --disable-network-manager \
    --enable-polkit \
    --disable-debug
}

build() {
  cd $pkgname
  make
}

package() {
  cd $pkgname
  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
