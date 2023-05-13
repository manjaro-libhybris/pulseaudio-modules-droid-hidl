# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>
# Contributor Erik Inkinen <erik.inkinen@gmail.com>

pkgname=pulseaudio-modules-droid-hidl
provides=('pulseaduio-modules-droid-hidl')
_pkgbase=pulseaudio-modules-droid-hidl
pkgver=9902.09074dc0
pkgrel=1
arch=('armv7h' 'aarch64' 'x86' 'x86_64')
url="https://github.com/mer-hybris/pulseaudio-modules-droid-hidl"
license=('GPL2')
depends=('pulseaudio-hybris' 'audiosystem-passthrough')
makedepends=('git' 'pkgconfig' 'android-headers' 'automake' 'autoconf' 'libhybris')
source=("pulseaudio-modules-droid-hidl::git+https://github.com/mer-hybris/pulseaudio-modules-droid-hidl.git")
provides=('pulseaudio-module-keepalive')
md5sums=('SKIP')
options=(debug !strip)

pkgver() {
  cd "${srcdir}/${_pkgbase}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "${srcdir}/${_pkgbase}"
  rm -rf build
  arch-meson  build
  ninja -C build
}

package() {
  cd "${srcdir}/${_pkgbase}"
  DESTDIR="${pkgdir}" ninja -C build install
}
