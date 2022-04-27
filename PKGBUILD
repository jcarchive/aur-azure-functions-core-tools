# Maintainer: Jose C.

pkgname=azure-functions-core-tools
pkgver=3.0.4502
pkgrel=1
pkgdesc='Tools for creating, developing, testing, running, and debugging Azure Functions'
arch=('x86_64')
options=('!strip')
url="https://github.com/Azure/azure-functions-core-tools"
license=('MIT')
provides=('func')
conflicts=('func')
_filename="Azure.Functions.Cli.linux-x64.$pkgver.zip"

source=("https://github.com/Azure/azure-functions-core-tools/releases/download/$pkgver/Azure.Functions.Cli.linux-x64.$pkgver.zip")

sha256sums=('49afed4dcc2ea90179d1a92c00c36233781c08da62ac7bbedacc1c2dd9da29c8')

package() {
	#Create directories with permission rwxr-xr-x
	install -m755 -d "$pkgdir/usr/share/$pkgname" "$pkgdir/usr/bin"

	cp -r $srcdir/* $pkgdir/usr/share/$pkgname
  chown -R root:root "$pkgdir/usr/share/$pkgname"
  chmod ugo+x $srcdir/func

	ln -s "/usr/share/${pkgname}/func" "$pkgdir/usr/bin/func"
}
