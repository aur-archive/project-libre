# Maintainer: Marat "Morion" Talipov <morion.self@gmail.com>

pkgname=project-libre
pkgver=1.5.6
pkgrel=1
pkgdesc="ProjectLibre is an open source project management software"
arch=('any')
url="http://www.projectlibre.org"
conflicts=('projectlibre')
license=('CPAL')
depends=('java-runtime')
install=.INSTALL
source=("http://downloads.sourceforge.net/project/projectlibre/ProjectLibre/${pkgver}/projectlibre-${pkgver}.tar.gz"
		"projectlibre.png"
		"projectlibre.desktop"
		"projectlibre.patch"
		"projectlibre.xml")
md5sums=('b8a7331583931ccce732f6ace5426a36'
         'cbeee50a6324b473c17899616f3effbd'
         'e93fab66e95915aaf9ef204d914b6e9f'
         'a223aba82618c7e486ff09b64ed9c703'
         '78bb62198c864aa6ac7a103c044f5b56')

build() {
	cd "$srcdir/projectlibre-$pkgver/"
	patch -p1 < $srcdir/projectlibre.patch
}

package() {
	cd "$srcdir/projectlibre-$pkgver/"	

	# Dirs
	install -dm 755 "${pkgdir}"/usr/bin
	install -dm 755 "${pkgdir}"/usr/share/pixmaps
	install -dm 755 "${pkgdir}"/usr/share/applications
	install -dm 755 "${pkgdir}"/usr/share/mime
	install -dm 755 "${pkgdir}"/usr/share/mime/packages
	install -dm 755 "${pkgdir}"/usr/share/doc/projectlibre
	install -dm 755 "${pkgdir}"/usr/share/doc/projectlibre/license
	install -dm 755 "${pkgdir}"/usr/share/doc/projectlibre/license/third-party	
	install -dm 755 "${pkgdir}"/usr/share/projectlibre
	install -dm 755 "${pkgdir}"/usr/share/projectlibre/lib

	#Files
	install -m644 $srcdir/projectlibre-$pkgver/projectlibre.jar "${pkgdir}"/usr/share/projectlibre/
	install -m644 $srcdir/projectlibre-$pkgver/lib/*.jar "${pkgdir}"/usr/share/projectlibre/lib
	install -m755 $srcdir/projectlibre-$pkgver/projectlibre.sh "${pkgdir}"/usr/bin/projectlibre
	install -m644 $srcdir/projectlibre-$pkgver/license/{index.html,index_html_0.gif,license.rtf} "${pkgdir}"/usr/share/doc/projectlibre/license
	install -m644 $srcdir/projectlibre-$pkgver/license/third-party/* "${pkgdir}"/usr/share/doc/projectlibre/license/third-party
	install -m644 $srcdir/projectlibre.png "${pkgdir}"/usr/share/pixmaps
	install -m644 $srcdir/projectlibre.desktop "${pkgdir}"/usr/share/applications
	install -m644 $srcdir/projectlibre.xml "${pkgdir}"/usr/share/mime/packages/

	msg "Done"
}

