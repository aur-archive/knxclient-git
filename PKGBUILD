# Author: vapourismo <ole@vprsm.de>

pkgname='knxclient-git'
pkgrel='4'
pkgver='r461.2e18868'
pkgdesc='A library which provides the means to communicate with several KNX-related devices or services.'
url='https://github.com/vapourismo/knxclient'
license='GPL2'

arch=('i686' 'x86_64' 'arm' 'armv6h' 'armv7h')
conflicts=('knxclient')
provides=('knxclient')
depends=('glibc')
makedepends=('git' 'make' 'coreutils' 'findutils')

source=("$pkgname::git+https://github.com/vapourismo/knxclient.git")
sha512sums=('SKIP')

pkgver() {
	cd "$srcdir/$pkgname"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "$srcdir/$pkgname"
	make && make test
}

package() {
	cd "$srcdir/$pkgname"
	make PREFIX="$pkgdir/usr" install
}
