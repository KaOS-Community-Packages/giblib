pkgname=giblib
pkgver=1.2.4
pkgrel=6
pkgdesc="A library that feh uses as a wrapper to imlib2"
arch=('x86_64')
url="http://freshmeat.net/projects/giblib/"
license=('MIT')
depends=('imlib2' 'libxext' 'freetype2')
source=("https://github.com/timcowchip/DISTFILES/raw/master/$pkgname-$pkgver.tar.gz")
sha256sums=('176611c4d88d742ea4013991ad54c2f9d2feefbc97a28434c0f48922ebaa8bac')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" docsdir=/usr/share/doc/giblib install

  # Install custom license
  install -Dm644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}