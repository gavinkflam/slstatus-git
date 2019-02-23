# Maintainer: Ankit R Gadiya <arch@argp.in>

pkgname=slstatus-git
_pkgname=slstatus
pkgver=r543.8de15fb
pkgrel=2
_commit=8de15fb3e9ea4475cd50f29d49ae0d08eab22e11
pkgdesc='A status monitor for window managers'
arch=('i686' 'x86_64')
url='http://tools.suckless.org/slstatus'
depends=('libx11' 'alsa-lib')
makedepends=('git')
license=('custom:ISC')
source=("git+https://github.com/gavinkflam/${_pkgname}.git#commit=${_commit}"
        "config.h")
md5sums=('SKIP'
         'SKIP')

prepare() {
  cp config.h "${_pkgname}/config.h"
}

build() {
  cd "${_pkgname}"
  make X11INC='/usr/include/X11' X11LIB='/usr/lib/X11'
}

package() {
  cd "${_pkgname}"
  make DESTDIR="${pkgdir}" PREFIX='/usr/' install

  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${_pkgname}/LICENSE"
}
