# Maintainer: Jonathan Mast <jon@jonmast.com>
# Based on nushell package, but uses prebuilt binary

pkgname=nushell-bin
pkgver=0.17.0
_underscoredpkgver=0_17_0
pkgrel=1
depends=('zlib' 'libxcb' 'openssl' 'libgit2')
optdepends=('libx11: for binaryview plugin')
arch=('i686' 'x86_64')
pkgdesc="A shell for the GitHub era"
conflicts=('nushell')
install=nushell-bin.install
source=("$pkgname-$pkgver.tar.gz::https://github.com/nushell/nushell/releases/download/$pkgver/nu_${_underscoredpkgver}_linux.tar.gz"
        "https://raw.githubusercontent.com/nushell/nushell/$pkgver/LICENSE")
url="http://nushell.sh"
license=('MIT')
sha256sums=('a7f5f3e7a7115e76b9d258b5fc1bf48813b3b5aa91760d3eb02564ac89d5836c'
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
