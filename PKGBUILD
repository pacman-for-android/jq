# Maintainer: Evgeniy Alekseev <arcanis at archlinux dot org>
# Contributor: Alex Chamberlain <alex at alexchamberlain dot co dot uk>
# Contributor: Kars Wang <jaklsy at gmail dot com>

pkgname=jq
pkgver=1.4
pkgrel=1
pkgdesc='Command-line JSON processor'
arch=('i686' 'x86_64')
url='http://stedolan.github.io/jq/'
license=('MIT')
depends=('glibc')
makedepends=('autoconf' 'automake' 'bison' 'flex' 'python2')
source=("http://stedolan.github.io/jq/download/source/${pkgname}-${pkgver}.tar.gz")
changelog=ChangeLog
md5sums=('e3c75a4f805bb5342c9f4b3603fb248f')

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
