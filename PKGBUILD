# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=scuttlebot
pkgver=11.3.3
pkgrel=1
pkgdesc="Secure scuttlebutt server"
arch=('x86_64')
url=""
license=('MITL')
groups=()
depends=('nodejs>=10.4.0-1')
makedepends=('npm')
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()

pkgver () {
  npm view scuttlebot-release@latest version
}

package () {
  local _npmdir="$pkgdir/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" scuttlebot-release@${pkgver}
}
