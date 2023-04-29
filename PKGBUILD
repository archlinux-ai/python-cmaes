# Maintainer: Benoît Allard <benoit.allard@gnx.de>
# Maintainer: Daniel Bershatsky <bepshatsky@yandex.ru>
pkgname=python-cmaes
_pkgname=${pkgname#python-}
pkgver=0.9.1
pkgrel=1
pkgdesc="Lightweight Covariance Matrix Adaptation Evolution Strategy (CMA-ES) implementation for Python 3"
arch=('any')
url="https://github.com/CyberAgent/cmaes"
license=('MIT')
depends=('python-numpy')
optdepends=('python-scipy: Support for CMA-WM.')
makedepends=('python-build' 'python-installer' 'python-setuptools' 'python-wheel')
source=("$_pkgname-$pkgver.tar.gz::https://github.com/CyberAgent/$_pkgname/archive/v$pkgver.tar.gz")
sha256sums=('57c8d7805b175ef821fd1940c46c10ef13b16ae5fd3018ea9bf186b53e5c4d13')

build() {
    cd $_pkgname-$pkgver
    python -m build -n -w
}

package() {
    python -m installer \
        --compile-bytecode 1 \
        --destdir="$pkgdir" \
        $_pkgname-$pkgver/dist/$_pkgname-*.whl
}
