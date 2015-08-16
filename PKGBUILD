# Maintainer: Stephane Sezer <sas@cd80.net>

_pkgname='mbdbdump'
pkgname="${_pkgname}-git"
pkgver=r34.ebd58f1
pkgrel=1
pkgdesc='Analyze contents of an iPhone backup in MBDB format.'
arch=('any')
_url="github.com/sas/${_pkgname}"
url="https://${_url}"
license=('BSD')
depends=('openssl')
makedepends=('git' 'ruby-ronn')
source=("repo::git://${_url}")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/repo"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build () {
  cd "${srcdir}/repo"
  make all
}

package () {
  cd "${srcdir}/repo"
  make PREFIX="${pkgdir}/usr" install
}
