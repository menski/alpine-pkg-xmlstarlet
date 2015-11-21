# Contributor: Sebastian Menski <sebastian@menski.org>
# Maintainer: Sebastian Menski <sebastian@menski.org>
pkgname=xmlstarlet
pkgver=1.6.1
pkgrel=1
pkgdesc="A set of tools to transform, query, validate, and edit XML documents"
url="http://xmlstar.sourceforge.net/"
arch="x86_64"
license="MIT"
depends="libxml2 libxslt"
depends_dev="libxml2-dev libxslt-dev"
makedepends="$depends_dev"
subpackages="$pkgname-doc"
source="http://downloads.sourceforge.net/xmlstar/$pkgname-$pkgver.tar.gz"

_builddir="$srcdir/$pkgname-$pkgver"
build() {
	cd "$_builddir"
	./configure \
		--build=$CBUILD \
		--host=$CHOST \
		--prefix=/usr \
		--sysconfdir=/etc \
		--mandir=/usr/share/man \
		--infodir=/usr/share/info \
		--localstatedir=/var \
		|| return 1
	make || return 1
}

package() {
	cd "$_builddir"
	make DESTDIR="$pkgdir" install || return 1
	rm -f "$pkgdir"/usr/lib/*.la
	ln -s xml "$pkgdir/usr/bin/xmlstarlet"
}

md5sums="f3c5dfa3b1a2ee06cd57c255cc8b70a0  xmlstarlet-1.6.1.tar.gz"
sha256sums="15d838c4f3375332fd95554619179b69e4ec91418a3a5296e7c631b7ed19e7ca  xmlstarlet-1.6.1.tar.gz"
sha512sums="4228df812caec7059d7a76986c4d9a4262bd861cc53dca05f341ae6c062be05f1c39fc637918ab00f60f40587c6c556e3c9bfaf8a18b149e3c321a92214dbe8b  xmlstarlet-1.6.1.tar.gz"
