# Maintainer: Giulio Girardi <giulio at rapgenic.it>

pkgname=hp-zbook-g5-tweaks
pkgver=0.0.1
pkgrel=1
pkgdesc="Support files for HP ZBook Studio G5 Mobile Workstation"
arch=('any')
url="https://github.com/rapgenic/hp-zbook-g5-tweaks"
license=('GPL2')
source=("https://github.com/rapgenic/${pkgname}/archive/${pkgver}.zip")
md5sums=('ae1adba835b7f28ef1f4f295a2183306')

package() {
  install -Dm0755 "$srcdir/${pkgname}-${pkgver}/sound/firmware/hpzbsg5.fw" "$pkgdir/usr/lib/firmware/hpzbsg5.fw"
  install -Dm0755 "$srcdir/${pkgname}-${pkgver}/sound/modprobe.d/hp-zbook-studio-g5-sound.conf" "$pkgdir//usr/lib/modprobe.d/hp-zbook-studio-g5-sound.conf"
}


