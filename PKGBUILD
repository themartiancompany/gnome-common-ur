# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2025  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Truocolo <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
# Maintainer: Pellegrino Prevete (dvorak) <pellegrinoprevete@gmail.com>
# Maintainer: Pellegrino Prevete (dvorak) <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
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
