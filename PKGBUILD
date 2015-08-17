# Maintainer: Jochen Schalanda <jochen+aur@schalanda.name>
_gemname=httpi
pkgname=ruby-$_gemname-1.1
pkgver=1.1.1
pkgrel=2
pkgdesc="Common interface for Ruby's HTTP libraries"
arch=(any)
url='https://github.com/savonrb/httpi'
license=('MIT')
depends=('ruby' 'ruby-rack')
source=(https://rubygems.org/downloads/$_gemname-$pkgver.gem)
noextract=($_gemname-$pkgver.gem)

package() {
  cd "$srcdir"
  # _gemdir is defined inside package() because if ruby[gems] is not installed on
  # the system, makepkg will exit with an error when sourcing the PKGBUILD.
  local _gemdir="$(ruby -rubygems -e'puts Gem.default_dir')"

  gem install --no-user-install --ignore-dependencies -i "$pkgdir$_gemdir" \
    -n "$pkgdir/usr/bin" "$_gemname-$pkgver.gem"
}
md5sums=('8521a6f43e460d14dc0cdedc8feb1a8c')
