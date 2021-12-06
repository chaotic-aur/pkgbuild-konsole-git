# Merged with official ABS kjsembed PKGBUILD by dr460nf1r3, 2021/12/05 (all respective contributors apply herein)
# Contributor: Felix Yan <felixonmars@archlinux.org>
# Contributor: Antonio Rojas <arojas@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=konsole-git
pkgver=21.11.90.r115.g6138b5470
pkgrel=1
arch=(x86_64)
url='https://apps.kde.org/konsole/'
pkgdesc='KDE terminal emulator'
license=(GPL LGPL FDL)
groups=(kde-applications-git kde-utilities-git)
depends=(knotifyconfig-git kpty-git kparts-git knewstuff-git)
makedepends=(extra-cmake-modules-git kdoctools-git)
conflicts=(${pkgname%-git})
provides=(${pkgname%-git})
optdepends=('keditbookmarks-git: to manage bookmarks')
source=(git+https://invent.kde.org/utilities/${pkgname%-git}.git)
sha256sums=('SKIP')

pkgver() {
    git -C ${pkgname%-git} describe --long | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cmake -B build -S ${pkgname%-git} \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
