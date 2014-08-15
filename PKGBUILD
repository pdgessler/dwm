# Maintainer: Paul Gessler <pdgessler@gmail.com>

pkgname=dwm-pdgessler
_gitname=dwm
pkgver=20140815015413.36c8b10
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
    cd "$_gitname"
    printf '%d.%s\n' "$(date -u -d "@$(git log -1 --format="%ct")" +%Y%m%d%H%M%S)" "$(git rev-parse --short HEAD)"
}

build() {
    cd "$_gitname"
    make
}

package() {
    cd "$_gitname"
    make PREFIX=/usr DESTDIR="$pkgdir" install
}
