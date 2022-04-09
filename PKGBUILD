# Maintainer: Hurstel Alexandre <alexandre at hurstel dot eu>
# Co-Maintainer: Tobias Manske <aur at rad4day dot de>
pkgname=xp-pen-tablet
pkgver=3.2.3.220323
epoch=1
pkgrel=1
pkgdesc="XP-Pen (Official) Linux utility (New UI driver)"
arch=('x86_64')
url='https://www.xp-pen.com/download/index.html'
license=('LGPL3')
conflicts=(xp-pen)
source=("XP-PEN-pentablet-${pkgver}-1.${CARCH}.tar.gz::https://www.xp-pen.ru/download/file/id/1942/pid/445/ext/gz.html"
        "install.sh.patch"
)
sha256sums=('70b6dc1345958c1858d091a3d48bdd75c91fcc879ba175739ef9152790bdcb2b'
            'faf485df1abc51a7cc0e9c605ecc4299dc5e17891ccea45467c3b9ee63fd7c62')

prepare() {
    cd "$srcdir/xp-pen-pentablet-${pkgver}-1.${CARCH}"

    patch < "$srcdir/install.sh.patch"
}


package() {
    cd "$srcdir/xp-pen-pentablet-${pkgver}-1.${CARCH}"

	mkdir -p "${pkgdir}/usr/lib/pentablet"
	mkdir -p "${pkgdir}/usr/share/applications"
	mkdir -p "${pkgdir}/usr/share/icons/"
	mkdir -p "${pkgdir}/etc/xdg/autostart"
	mkdir -p "${pkgdir}/usr/lib/udev/rules.d/"

	./install.sh "${pkgdir}"
}
