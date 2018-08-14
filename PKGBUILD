# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=scuttlebot
pkgver=11.3.3
pkgrel=3
pkgdesc="Secure scuttlebutt server"
arch=('x86_64')
url=""
license=('MITL')
groups=()
depends=('nodejs=10.8.0-2')
makedepends=('npm')
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
source=('sbot@.service')

sha256sums=('09493f9f3edc39ea61c58da30ab2b1df803b65734437e946d1276c0c74d1a5ca')

pkgver () {
  npm view scuttlebot-release@latest version
}

package () {
  install -Dm 644 -t "${pkgdir}/usr/lib/systemd/system" "sbot@.service"
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" scuttlebot-release@${pkgver}
}
