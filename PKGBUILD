# Maintainer: Benoît Allard <benoit.allard@gnx.de>
# Maintainer: Daniel Bershatsky <bepshatsky@yandex.ru>
pkgname=python-cmaes
_pkgname=${pkgname#python-}
pkgver=0.10.0
pkgrel=1
pkgdesc="Lightweight Covariance Matrix Adaptation Evolution Strategy (CMA-ES) implementation for Python 3"
arch=('any')
url="https://github.com/CyberAgent/cmaes"
license=('MIT')
depends=('python-numpy')
optdepends=('python-scipy: Support for CMA-WM.')
makedepends=('python-build' 'python-installer' 'python-setuptools' 'python-wheel')
source=("$_pkgname-$pkgver.tar.gz::https://github.com/CyberAgent/$_pkgname/archive/v$pkgver.tar.gz")
sha256sums=('d6a5b8e7a25390ba1f83d6426a1f79d9ba3d46d3d82f79e0fb945668f51af1b1')

build() {
    python -m build -nw $_pkgname-$pkgver
}

package() {
    python -m installer \
        --compile-bytecode 1 \
        --destdir="$pkgdir" \
        $_pkgname-$pkgver/dist/$_pkgname-*.whl
}
