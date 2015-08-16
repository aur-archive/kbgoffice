# Maintainer: mikkie <kriha6@abv.bg>

pkgname=kbgoffice
pkgver=2.1
pkgrel=4
pkgdesc="Bulgarian Dictionary (Qt4 version)"
arch=('i686' 'x86_64')
url=http://bgoffice.sourceforge.net/assistant/index.html
license=('GPL2' 'unknown')
depends=('qt4')
source=($pkgname-$pkgver.tar.gz::'http://sourceforge.net/projects/bgoffice/files/BG%20Office%20Assistant/$pkgver/$pkgname-$pkgver.tar.gz/download'
        full-pack.tar.bz2::'http://sourceforge.net/projects/bgoffice/files/Full%20Pack%20of%20Dictionaries/1.0/full-pack.tar.bz2/download'
)
md5sums=(
    'ec70b750f6cc23a0ad7938fefb614ad8' 
    '5211fcc86bda7b9a87255aa982d7b135'
)

build() {
  cd "$srcdir/$pkgname-$pkgver/src"
  qmake-qt4 -config -release
  make clean
}

package() {
  cd "$srcdir/$pkgname-$pkgver/src"
  make INSTALL_ROOT="$pkgdir/" install

  cd "${srcdir}/full-pack/data"
  install -m 644 -D * "$pkgdir/usr/local/share/bgoffice"
}
