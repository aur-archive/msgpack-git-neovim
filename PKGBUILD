# Contributor: Leen Jewel <leenjewel@gmail.com>
# Contributor: Auguste Pop <auguste [at] gmail [dot] com>
# Maintainer: Florian Walch <florian+aur@fwalch.com>

pkgname=msgpack-git-neovim
_commit=f6d0cd9a4ba46f4341014a199e3d352fad76b215
pkgrel=2
pkgver=0.r1642.f6d0cd9
pkgdesc="An efficient object serialization library; experimental version needed for neovim-git."
arch=('i686' 'x86_64')
url="http://msgpack.org/"
license=('Apache')
makedepends=('git')
conflicts=('msgpack-c' 'msgpack-c-git')
provides=('msgpack-c')
source=("${pkgname}::git://github.com/msgpack/msgpack-c.git#commit=${_commit}")
md5sums=('SKIP')

pkgver() {
  cd "${pkgname}"
  printf "0.r%s.%s" "$(git rev-list --count ${_commit})" "$(git rev-parse --short HEAD)"
}

build() {
  cd "${pkgname}"
  ./bootstrap
  ./configure --prefix=/usr
  make
}

package() {
  cd "${pkgname}"
  make DESTDIR=${pkgdir} install
}

# vim:set sw=2 sts=2 et:
