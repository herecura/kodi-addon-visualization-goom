# $Id$
# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-visualization-goom
_commit=16747b7
pkgver=20151116.16747b7
pkgrel=2
pkgdesc="GOOM visualizer for Kodi"
arch=('i686' 'x86_64')
url='github.com/notspiff/visualization.goom'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-visualization')
depends=('kodi')
makedepends=('git' 'cmake')
source=("$pkgname::git://github.com/notspiff/visualization.goom.git#commit=$_commit")
sha256sums=('SKIP')

pkgver() {
	cd "$pkgname"
	git log -1 --date=short --format="%cd.%h" | tr -d '-'
}

build() {
	cd "$pkgname"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
	cd "$pkgname"
	make DESTDIR="$pkgdir/" install
}

