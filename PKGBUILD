# Maintainer: garion < garion @ mailoo.org >
# Contributor: Eric Forgeot < http://ifiction.free.fr >

pkgname=utrac
pkgver=0.3.0
pkgrel=3
pkgdesc="CLI tool for recognizing the encoding and the end-of-line type of a file"
arch=(i686 x86_64)
url="http://utrac.sourceforge.net/"
license=('GPL')
depends=('glibc')
source=(http://utrac.sourceforge.net/download/$pkgname-$pkgver.tar.gz)
md5sums=(0b70a94e450d428bc49d499110052ae6)

build(){
    cd $srcdir/$pkgname-$pkgver
    sed -i -e 's/PREFIX_PATH = \/usr\/local/PREFIX_PATH = \/usr/g' Makefile
    make prefix=${pkgdir}/usr
}

package(){
    cd $srcdir/$pkgname-$pkgver
    strip utrac
    install -Dm755 utrac        $pkgdir/usr/bin/utrac
    #install -Dm644 libutrac.a   $pkgdir/usr/lib/libutrac.a
    install -Dm644 charsets.dat $pkgdir/usr/share/utrac/charsets.dat
    install -Dm644 utrac.1      $pkgdir/usr/share/man/man1/utrac.1
}
