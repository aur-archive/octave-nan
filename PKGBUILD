#
# Maintainer: Clemens Buchacher <drizzd@aon.at>
#
# You can use the newpkg script from
# https://github.com/drizzd/octave-forge-archlinux to automatically generate
# new octave-forge PKGBUILDs or update existing ones. Patches welcome.
#

_pack=nan
pkgname=octave-$_pack
pkgver=2.7.4
pkgrel=1
pkgdesc="A statistics and machine learning toolbox for data with and w/o missing values"
arch=(any)
url="http://octave.sourceforge.net/$_pack/"
license=('GPL3')
groups=('octave-forge')
depends=('octave>3.2.0')
makedepends=()
optdepends=()
backup=()
options=(!makeflags)
install=$pkgname.install
_archive=$_pack-$pkgver.tar.gz
source=("http://downloads.sourceforge.net/octave/$_archive")
noextract=("$_archive")
md5sums=('5c7dfe9b8f29da7e289f8bb772230b72')

build() {
  cd "$srcdir"
  mkdir -p builddir
  octave -q -f --eval "pkg build -verbose -nodeps builddir $_archive"
}

package() {
  mkdir -p "$pkgdir/usr/share/octave/packages"
  mkdir -p "$pkgdir/usr/lib/octave/packages"
  cp "$srcdir/builddir/$_archive" "$pkgdir/usr/share/octave/$_pack.tar.gz"
}
