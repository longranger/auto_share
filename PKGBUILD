# Maintainer: longranger <longranger dot 406 at gmail dot com>
pkgname="auto_share"
pkgver="0.1.0"
pkgrel=1
url="https://github.com/longranger/auto_share"
pkgdesc="auto mount nfs shares per archwiki"
arch=('x86_64')
license=('GPL')
depends=()
makedepends=('git')
source=("${pkgname}-${pkgver}"::'git://github.com/longranger/auto_share')
md5sums=('SKIP')
install='auto_share.install'

pkgver() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	# Use the tag of the last commit
	git describe --long | sed -E 's/([^-]*-g)/r\1/;s/-/./g'
}
package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	install -Dm755 auto_share "${pkgdir}"/usr/bin/auto_share
	install -Dm755 auto_share.timer "${pkgdir}"/etc/systemd/system/auto_share.timer
	install -Dm755 auto_share.service "${pkgdir}"/etc/systemd/system/auto_share.service
}
