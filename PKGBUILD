# Maintainer: Paul Gessler <pdgessler@gmail.com>

pkgname=dwm-pdgessler
_gitname=dwm
pkgver=20140812064552.74ffb3e
pkgrel=1
pkgdesc="A dynamic window manager for X - pdgessler personalizations"
license=( "MIT" )
url="https://github.com/pdgessler/dwm"
depends=('libx11' 'libxinerama')

arch=( "any" )
makedepends=( "git" )
conflicts=( "dwm" )
provides=( "dwm" )
source=(
    "git://github.com/pdgessler/dwm.git"
)
md5sums=(
    "SKIP"
)

pkgver() {
    printf '%d.%s\n' "$(date -u -d "@$(git log -1 --format="%ct")" +%Y%m%d%H%M%S)" "$(git rev-parse --short HEAD)"
}

build() {
    make
}

package() {
    make PREFIX=/usr DESTDIR="$pkgdir" install
}
