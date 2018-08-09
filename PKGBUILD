# Maintainer: Ankit R Gadiya <arch@argp.in>

pkgname=slstatus-git
_pkgname=slstatus
pkgver=r540.dd7f189
pkgrel=1
_commit=dd7f1896aa9883f33b4d28cd192e8088db0cab5a
pkgdesc='A status monitor for window managers'
arch=('i686' 'x86_64')
url='http://tools.suckless.org/slstatus'
depends=('libx11')
makedepends=('git')
license=('custom:ISC')
source=("git+git://git.suckless.org/${_pkgname}#commit=${_commit}"
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
