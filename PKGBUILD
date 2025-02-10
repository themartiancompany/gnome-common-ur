# Maintainer: Jan de Groot <jgc@archlinux.org>

_os="$( \
  uname \
    -o)"
if [[ "${_os}" == "Android" ]]; then
  _shell="bash"
elif [[ "${_os}" == "GNU/Linux" ]]; then
  _shell="sh"
fi
_proj="gnome"
pkgname="${_proj}-common"
pkgver=3.18.0
pkgrel=6
pkgdesc="Common development macros for GNOME"
arch=(
  'any'
)
depends=(
  "${_shell}"
  'autoconf-archive'
  'intltool'
  'yelp-tools'
  'gtk-doc'
)
license=(
  'GPL'
)
url="https://www.${_proj}.org"
_http="https://download.${_proj}.org"
_ns="sources"
_url="${_http}/${_ns}/${pkgname}"
source=(
  "${_url}/${pkgver:0:4}/${pkgname}-${pkgver}.tar.xz"
)
sha256sums=(
  '22569e370ae755e04527b76328befc4c73b62bfd4a572499fde116b8318af8cf'
)

build() {
  cd \
    "${pkgname}-${pkgver}"
  ./configure \
    --prefix="/usr" \
    --with-autoconf-archive
  make
}

package() {
  cd \
    "${pkgname}-${pkgver}"
  make \
    DESTDIR="${pkgdir}" \
    install
}
