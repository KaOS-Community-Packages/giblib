pkgname=giblib
pkgver=1.2.4
pkgrel=6
pkgdesc="A library that feh uses as a wrapper to imlib2"
arch=('x86_64')
url="http://freshmeat.net/projects/giblib/"
license=('MIT')
depends=('imlib2' 'libxext' 'freetype2')
source=("https://github.com/timcowchip/DISTFILES/blob/master/$pkgname-$pkgver.tar.gz")
md5sums=('c810ef5389baf24882a1caca2954385e')

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