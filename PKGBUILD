# Maintainer: Jose C.

pkgname=azure-functions-core-tools
pkgver=4.0.4483
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

sha256sums=('988f35286c16b9d9ac8bad778707b7d2bd63d0c179bea0092c9e25b1b1193b50')

package() {
	#Create directories with permission rwxr-xr-x
	install -m755 -d "$pkgdir/usr/share/$pkgname" "$pkgdir/usr/bin"

  #rm $srcdir/func.deps.json
	cp -r $srcdir/* $pkgdir/usr/share/$pkgname
  chown -R root:root "$pkgdir/usr/share/$pkgname"
  echo -e "#!/bin/bash\n" "DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=1 /usr/share/$pkgname/func" '$@' > $pkgdir/usr/share/$pkgname/func-wrapper

  chmod ugo+x $pkgdir/usr/share/$pkgname/func
  chmod ugo+x $pkgdir/usr/share/$pkgname/gozip
  chmod ugo+x $pkgdir/usr/share/$pkgname/createdump
  chmod ugo+x $pkgdir/usr/share/$pkgname/func-wrapper

	ln -s "/usr/share/${pkgname}/func-wrapper" "$pkgdir/usr/bin/func"
}
