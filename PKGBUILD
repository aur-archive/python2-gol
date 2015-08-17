# Maintainer: Reihar <reihar@necronomicon.fr>
pkgname=python2-gol
pkgver=0.76.r1.g55424d7
pkgrel=1
pkgdesc="A python implementation of Conway's Game of Life using the curses module with a small evolutionary twist."
arch=('i686' 'x86_64')
url="https://github.com/iiSeymour/game-of-life"
license=('MIT')
depends=('python2')
makedepends=('git')
options=(!emptydirs)
install=python2-gol.install
source=(git+https://github.com/iiSeymour/game-of-life.git
	'0001-Changing-the-shebang-for-python2.patch'
	'0001-Change-setup.py-s-shebang.patch')
md5sums=('SKIP'
	'85ebbf6abbe1dff1a35943fb18c14aae'
	'ab5aa931a4051d24a7b4889dda72fcfc')

pkgver() {
  cd "$srcdir/game-of-life"
  git describe --long --tags | sed -r 's/^v//;s/([^-]*-g)/r\1/;s/-/./g'
}

package() {
  cd "$srcdir/game-of-life"
  git am ../0001-Changing-the-shebang-for-python2.patch
  git am ../0001-Change-setup.py-s-shebang.patch
  python2 setup.py install --root="$pkgdir/" --optimize=1
}