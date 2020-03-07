# Maintainer: Giulio Girardi <giulio at rapgenic.it>

pkgname=hp-zbook-g5-tweaks
pkgver=0.0.1
pkgrel=1
pkgdesc="Support files for HP ZBook Studio G5 Mobile Workstation"
arch=('any')
url="https://github.com/rapgenic/hp-zbook-g5-tweaks"
license=('GPL2')
source=("https://github.com/rapgenic/${pkgname}/archive/${pkgver}.zip")
md5sums=('9cffd6cb171dbb3cfcc1c4f01bfd3d78')

package() {
  install -Dm0755 "$srcdir/${pkgname}-${pkgver}/sound/firmware/hpzbsg5.fw" "$pkgdir/lib/firmware/hpzbsg5.fw"
  install -Dm0755 "$srcdir/${pkgname}-${pkgver}/sound/modprobe.d/hp-zbook-studio-g5-sound.conf" "$pkgdir//usr/lib/modprobe.d/hp-zbook-studio-g5-sound.conf"
}


