#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-glyphsets/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-glyphsets/discussions>

_langname="python"
_relname="openstep_plist"
_pacname="openstep-plist"

pkgname="${_langname}-${_pacname}"
pkgver=0.3.0
pkgrel=1
pkgdesc="OpenStep plist parser and writer written in Cython"
arch=(
  "x86_64"
)
url="https://github.com/fonttools/openstep-plist"
license=(
  "MIT"
)
depends=(
  "python"
)
makedepends=(
  "cython"
  "python-setuptools-scm"
)
checkdepends=(
  "python-pytest"
)
_zipname="${_relname}-${pkgver}"
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/${_zipname}.zip"
)
sha512sums=(
  "2ce7f520ab336b68d3bb48854b164e61601e7a13bc30f89e4d191536b4609e1f50d973c202fb3a5c74f7718e005ce20db91ba3ca8f2a95241f251af1bbf8cb8d"
)

build() {

  cd "${_zipname}"

  python setup.py build
}

check() {

  cd "${_zipname}"

  python setup.py test
}

package() {

  cd "${_zipname}"

  python setup.py install --root="$pkgdir" --optimize=1 --skip-build
}
