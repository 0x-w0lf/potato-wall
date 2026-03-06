pkgname=potato-wall
pkgver=1.0.0
pkgrel=1
pkgdesc="Dynamic network security and firewall manager with 3 hardening levels"
arch=('any')
url="https://potatolabs.tech"
license=('GPL')
depends=('ufw' 'networkmanager' 'curl' 'bash')
install='potato-wall.install'
source=('potato-wall')
sha256sums=('SKIP')

package() {
  install -dm755 "$pkgdir/usr/bin"
  install -m755 "$srcdir/potato-wall" "$pkgdir/usr/bin/potato-wall"
}
