# Maintainer: Evgeniy Alekseev <arcanis at archlinux dot org>
# Contributor: Alex Chamberlain <alex at alexchamberlain dot co dot uk>
# Contributor: Kars Wang <jaklsy at gmail dot com>

pkgname=jq
pkgver=1.7
pkgrel=1
pkgdesc='Command-line JSON processor'
arch=('x86_64')
url='https://stedolan.github.io/jq/'
license=('MIT')
depends=('glibc' 'oniguruma')
makedepends=('autoconf' 'automake' 'bison' 'flex' 'python')
source=("https://github.com/jqlang/jq/releases/download/${pkgname}-${pkgver}/${pkgname}-${pkgver}.tar.gz")
changelog=ChangeLog
sha512sums=('4f8a6b0401e6c881dcb97d948fe38871062599a43fff667ede21cf185ec9de33e61878f0a6ea12786d0a632eea592ea0ff860520ba02dbb32f2fa2d2b5db7a0a')

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

