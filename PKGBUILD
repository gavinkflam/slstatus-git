# Maintainer: Ankit R Gadiya <arch@argp.in>

pkgname=slstatus-git
_pkgname=slstatus
pkgver=r542.d3197e5
pkgrel=1
_commit=d3197e5e3a679399443f3a2a825ed80d75e925a1
pkgdesc='A status monitor for window managers'
arch=('i686' 'x86_64')
url='http://tools.suckless.org/slstatus'
depends=('libx11' 'alsa-lib')
makedepends=('git')
license=('custom:ISC')
source=("git+https://gitlab.com/gavinkflam/${_pkgname}.git#commit=${_commit}"
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
