# Maintainer: Evgeniy Alekseev <arcanis at archlinux dot org>
# Contributor: Alex Chamberlain <alex at alexchamberlain dot co dot uk>
# Contributor: Kars Wang <jaklsy at gmail dot com>

pkgname=jq
pkgver=1.5
pkgrel=5
pkgdesc='Command-line JSON processor'
arch=('i686' 'x86_64')
url='http://stedolan.github.io/jq/'
license=('MIT')
depends=('glibc' 'oniguruma')
makedepends=('autoconf' 'automake' 'bison' 'flex' 'python2')
source=("https://github.com/stedolan/jq/releases/download/${pkgname}-${pkgver}/${pkgname}-${pkgver}.tar.gz"
        "cve-2015-8863.patch::https://github.com/stedolan/jq/commit/8eb1367ca44e772963e704a700ef72ae2e12babd.patch")
changelog=ChangeLog
md5sums=('0933532b086bd8b6a41c1b162b1731f9'
         '104f363774c8f312943db55a4dd59ac6')

prepare() {
    cd "${pkgname}-${pkgver}"
    patch -p2 -i "${srcdir}/cve-2015-8863.patch"
}

build() {
    cd "${pkgname}-${pkgver}"
    ./configure --prefix=/usr
    make
}

package() {
    cd "${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" prefix=/usr install
    install -Dm644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/COPYING"
}
