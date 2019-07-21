pkgname='semblance'
pkgdesc="Basic disassembler for the 16-bit protected NE windows executables among others"
pkgver=r145.cbdadd3
pkgrel=1
arch=('any')
source=('semblance::git+https://github.com/zfigura/semblance#branch=master')
md5sums=('SKIP')
pkgver() {
    cd "$pkgname"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
    cd "$pkgname"
    ./autogen.sh
    ./configure --prefix=/usr
    make
}

package() {
    mkdir -p $pkgdir/usr/bin
    cp -p "$srcdir/$pkgname/dump" "$pkgdir/usr/bin/dumpne"
}
