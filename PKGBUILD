# Maintainer: Elia Notarangelo <elia.notarangelo AT gmail DOT com>
# Contributor: Frikilinux <frikilinux at frikilinux.com.ar>
# Contributor: graysky <graysky AT archlinux DOT us>
# Contributor: Samsagax <samsagax AT gmail DOT com>
# Contributor: simongmzlj <simongmzlj AT gmail DOT com>

pkgname=faenza-icon-theme
pkgver=1.3.1
pkgrel=1
pkgdesc="Icon theme designed for Equinox GTK theme"
url="http://gnome-look.org/content/show.php/Faenza?content=128143"
license=('GPL3')
arch=('any')
makedepends=()
options=(!strip)
source=("http://ppa.launchpad.net/tiheum/equinox/ubuntu/pool/main/f/${pkgname}/${pkgname}_${pkgver}.tar.gz")

package() {
	cd "${srcdir}"/"$pkgname"-1.3
	mkdir -p "${pkgdir}"/usr/share/icons
	mkdir -p "${pkgdir}"/usr/lib
	mkdir -p "${pkgdir}"/usr/share

	cp -rf Faenza{,-Dark,-Darkest,-Darker,-Ambiance,-Radiance} "${pkgdir}"/usr/share/icons/
	cp -rf rhythmbox "${pkgdir}"/usr/lib/
	cp -rf emesene "${pkgdir}"/usr/share/

	# set the Arch Linux Distributor and start menu logo
	for theme in Faenza{,-Dark}; do
		for size in 22 24 32 48 64 96; do
			cd "${pkgdir}"/usr/share/icons/${theme}/places/${size}/
			ln -sf distributor-logo{-archlinux,}.png
			ln -sf start-here{-archlinux,}.png
		done;
		cd "${pkgdir}"/usr/share/icons/${theme}/places/scalable/
		ln -sf distributor-logo{-archlinux,}.svg
		ln -sf start-here{-archlinux,}.svg
		ln -sf start-here{-archlinux-symbolic,-symbolic}.svg
	done;

}


md5sums=('b5339b70cbb821b583499e725957b150')
