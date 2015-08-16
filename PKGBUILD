# Maintainer: Gerardo Exequiel Pozzi <vmlinuz386@yahoo.com.ar>

pkgname=libbsd
pkgver=0.3.0
pkgrel=1
pkgdesc="Provides useful functions commonly found on BSD systems like strlcpy()"
arch=('i686' 'x86_64')
url="http://libbsd.freedesktop.org"
license=('custom')
depends=('glibc')
changelog='ChangeLog'
source=(http://libbsd.freedesktop.org/releases/$pkgname-$pkgver.tar.gz
        LICENSE)
md5sums=('833e58531b4bd84b119b53d834d8e0d8'
         '5bd59ff83a7df4873b034478ffae62a6')

build() {
  cd $srcdir/$pkgname-$pkgver

  make exec_prefix=/usr includedir=/usr/include/libbsd || return 1
}

package() {
  cd $srcdir/$pkgname-$pkgver

  make exec_prefix=/usr includedir=/usr/include/libbsd DESTDIR=$pkgdir install
  install -D -m644 $srcdir/LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
}

# vim:set ts=2 sw=2 et:
