# Maintainer: Jonathan Mast <jon@jonmast.com>
# Contributor: Hoàng Văn Khải <hvksmr1996@gmail.com>
# Based on nushell package, but uses prebuilt binary

pkgname=nushell-bin
pkgver=0.24.0
_underscoredpkgver="${pkgver//./_}"
pkgrel=1
depends=('zlib' 'libxcb' 'openssl' 'libgit2')
optdepends=('libx11: for binaryview plugin')
arch=('i686' 'x86_64')
pkgdesc="A new type of shell"
provides=('nushell')
conflicts=('nushell')
install=nushell-bin.install
source=("$pkgname-$pkgver.tar.gz::https://github.com/nushell/nushell/releases/download/$pkgver/nu_${_underscoredpkgver}_linux.tar.gz"
        "https://raw.githubusercontent.com/nushell/nushell/$pkgver/LICENSE")
url="http://nushell.sh"
license=('MIT')
sha256sums=('df3a62263b3fc86b8eae7dde0549ddf25dcb1fb7ab7f0fbf55848c58dd896344'
            '57fdb6634a2372af0978dd178f8e157f227d96f3ca27ae9c73f1320f6c0c41d4')

build() {
  return 0
}

package() {
  install -dm755 "${pkgdir}/usr/bin/"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"

  cd "$srcdir/nu_${_underscoredpkgver}_linux/nushell-${pkgver}"

  # Install nu and plugins into /usr/bin
  cp nu "${pkgdir}/usr/bin/nu"
  cp nu_plugin_* "${pkgdir}/usr/bin/"
}
