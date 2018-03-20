# Maintainer: Evgeniy Alekseev <arcanis at archlinux dot org>
# Contributor: Alex Chamberlain <alex at alexchamberlain dot co dot uk>
# Contributor: Kars Wang <jaklsy at gmail dot com>

pkgname=jq
pkgver=1.5
pkgrel=6
pkgdesc='Command-line JSON processor'
arch=('x86_64')
url='http://stedolan.github.io/jq/'
license=('MIT')
depends=('glibc' 'oniguruma')
makedepends=('autoconf' 'automake' 'bison' 'flex' 'python2')
source=("https://github.com/stedolan/jq/releases/download/${pkgname}-${pkgver}/${pkgname}-${pkgver}.tar.gz"
        "cve-2015-8863.patch::https://github.com/stedolan/jq/commit/8eb1367ca44e772963e704a700ef72ae2e12babd.patch")
changelog=ChangeLog
sha512sums=('4a0bb069ae875f47731d7d84ae6b82240703dc7a694cfb0aee4c7e9639defe7ba9af575d17dc32bda4426b80c186cc8dcd4505f3a6bcbe16b39e9b13097da238'
            'a247d7bd9ba7186d475852f7f41be1974071a4c27a1b358b80912bab19463df24b5ed5210172c84d205f8a390f0718bc834b8ca9672f9a192dc947e92d4e5f19')

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

