pkgname=materialize
pkgver=0.26.4
pkgrel=1
pkgdesc="Materialize is a streaming database for real-time applications."
arch=('any')
url="https://materialize.com"
license=('custom')
groups=()
depends=()
makedepends=('git' 'rust>=1.6.0') # 'bzr', 'git', 'mercurial' or 'subversion'
provides=("${pkgname}")
conflicts=("${pkgname}")
source=("git+https://github.com/MaterializeInc/materialize.git#commit=v${pkgver}")
md5sums=('SKIP')

build() {
	cd "$srcdir/${pkgname}"
    cargo build --release --bin materialized
}


package() {
	cd "$srcdir/${pkgname}"
    install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    install -Dm644 "$srcdir/${pkgname}/target/release/materialized" "${pkgdir}/usr/bin/materialized"
}
