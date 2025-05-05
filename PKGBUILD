# Maintainer: loathingkernel <loathingkernel _a_ gmail _d_ com>

pkgname=umu-launcher
pkgver=1.2.6
pkgrel=1
pkgdesc="The Unified Launcher for Windows Games on Linux, to run Proton with fixes outside of Steam"
arch=('x86_64')
url="https://github.com/Open-Wine-Components/umu-launcher"
license=('GPL-3.0-only')
source=("git+https://github.com/Open-Wine-Components/umu-launcher.git")
sha256sums=('SKIP')
depends=(
  python
  python-xlib
  python-filelock
  lib32-vulkan-driver
  lib32-opengl-driver
  python-pyzstd
  python-urllib3
)
makedepends=(
  git
  scdoc
  python-build
  python-installer
  python-hatchling
  python-pip
)

prepare() {
  cd "$srcdir"/umu-launcher
}

build() {
  cd "$srcdir"/umu-launcher
  ./configure.sh --prefix=/usr --use-system-pyzstd --use-system-urllib
  make
}

package() {
  cd "$srcdir"/umu-launcher
  make DESTDIR="$pkgdir" install
}
