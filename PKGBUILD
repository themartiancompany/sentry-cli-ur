# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer:  Pellegrino Prevete <cGVsbGVncmlub3ByZXZldGVAZ21haWwuY29tCg== | base -d>
# Maintainer:  Truocolo <truocolo@aol.com>
# Maintainer:  Sven-Hendrik Haase <svenstaro@archlinux.org>
# Contributor: Bambang Catur Pamungkas <bambangcaturz@gmail.com>

pkgname=sentry-cli
pkgver=2.20.6
pkgrel=1
pkgdesc="A command line utility to work with Sentry"
arch=(
  'x86_64'
  'arm'
  'aarch64'
  'mips'
  'armv7h'
)
url="https://docs.sentry.io/cli/"
license=('BSD')
depends=('gcc-libs' 'bzip2' 'zlib')
makedepends=('cargo')
options=('!lto')
source=("$pkgname-$pkgver.tar.gz"::https://github.com/getsentry/sentry-cli/archive/${pkgver}.tar.gz)
sha256sums=('bc60cc1a6015c337e7a3598123962dd24564426bd1a537f759fd19b00184643e')

build() {
  cd $pkgname-$pkgver
  cargo build --release --locked
}

package() {
  cd $pkgname-$pkgver
  install -Dm755 target/release/sentry-cli "$pkgdir"/usr/bin/sentry-cli
  install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}

# vim:set sw=2 sts=-1 et:
