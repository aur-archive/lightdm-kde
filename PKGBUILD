# Maintainer: Massimiliano Torromeo <massimiliano.torromeo@gmail.com>
# Contributor: Mladen Pejakovic <pejakm@gmail.com>
# Contributor: Xiao-Long Chen <chenxiaolong@cxl.epac.to>

pkgname=lightdm-kde
pkgver=0.3.1
pkgrel=2
pkgdesc="LightDM Greeter for KDE"
arch=('i686' 'x86_64')
url="https://projects.kde.org/projects/playground/base/lightdm"
license=('GPL')
depends=('lightdm' 'openssl' 'perl' 'phonon' 'kdelibs')
makedepends=('cmake' 'automoc4')
install=lightdm-kde.install
source=("ftp://ftp.kde.org/pub/kde/unstable/$pkgname/src/$pkgname-$pkgver.tar.bz2")

build() {
	cd "$srcdir/lightdm-$pkgver/"
	cmake . \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DQT_QMAKE_EXECUTABLE=qmake-qt4
	make
}

package() {
	cd "$srcdir/lightdm-$pkgver"
	make DESTDIR="$pkgdir" install
}

sha256sums=('855cffaccc6500e25016e104cd593189cad9aa88ee34f237b01964fce1bcfcf9')
