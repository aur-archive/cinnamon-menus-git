# $Id$
# Maintainer: Realex
# Based on cinnamon-menus PKGBUILD

_pkgname=cinnamon-menus
pkgname=${_pkgname}-git
pkgver=16.079b46d
pkgrel=1
pkgdesc="Cinnamon menu specifications"
arch=('i686' 'x86_64')
depends=('glib2')
makedepends=('intltool' 'gobject-introspection')
conflicts=(${_pkgname})
provides=(${_pkgname})
license=('GPL' 'LGPL')
url="https://github.com/linuxmint/cinnamon-menus"
source=("${_pkgname}"::git+https://github.com/linuxmint/cinnamon-menus.git)
sha256sums=('SKIP')

pkgver() {
  cd "${srcdir}/${_pkgname}"
  echo $(git rev-list --count master).$(git rev-parse --short master)
}

build() {
  cd "${srcdir}/${_pkgname}"
  ./configure \
      --prefix=/usr --sysconfdir=/etc \
      --localstatedir=/var  --disable-static \
      --sbindir=/usr/bin
  make
}

package(){
  cd "${srcdir}/${_pkgname}"
  make DESTDIR="$pkgdir" install
}
