# Maintainer: Bert Peters <bert@bertptrs.nl>
pkgname=simdjson
pkgver=2.2.1
pkgrel=1
pkgdesc="A C++ library to see how fast we can parse JSON with complete validation."
arch=('x86_64')
url="https://github.com/simdjson/simdjson"
license=('APACHE')
depends=(gcc-libs)
makedepends=(cmake)
source=("$pkgname-$pkgver.tar.gz::https://github.com/simdjson/simdjson/archive/v$pkgver.tar.gz")
sha256sums=('a2a22b9e1cb7310bc3957763f51b4526a60ab6f4db777d8f728f14ad8ff69e3d')

build() {
	cd "$pkgname-$pkgver"
	cmake . -DCMAKE_INSTALL_PREFIX="/usr/" -DBUILD_SHARED_LIBS=On
	make
}

# Running tests requires enabling developer mode, which greatly increases the
# required compilation, so we don't.
#
# Also tests refuse to compile with current GCC
# check() {
# 	cd "$pkgname-$pkgver"
# 	make test
# }

package() {
	cd "$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" install
}
