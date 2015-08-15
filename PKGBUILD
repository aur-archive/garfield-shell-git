# Maintainer: Vincent Schüßler <v.schuessler@gmail.com>
pkgname=garfield-shell-git
pkgver=r64.a05fce8
pkgrel=1
pkgdesc="Shell tools for interfacing Garfield (FSMI POS System)"
arch=('i686' 'x86_64')
url="https://github.com/kitinfo/garfield-shell"
license=('unknown')
depends=('postgresql-libs')
source=("$pkgname"::'git+https://github.com/kitinfo/garfield-shell.git')
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/$pkgname"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "$srcdir/$pkgname"
	make
}

package() {
	cd "$srcdir/$pkgname"
	DEST="$pkgdir/usr/bin"
	mkdir -p $DEST
	make INSTALLPATH=$DEST install
}
