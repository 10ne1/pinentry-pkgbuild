# $Id$
# Maintainer: Tobias Powalowski <tpowa@archlinux.org>
# Maintainer: Gaetan Bisson <bisson@archlinux.org>

pkgname=pinentry
pkgver=1.0.0
pkgrel=1
pkgdesc='Collection of simple PIN or passphrase entry dialogs which utilize the Assuan protocol'
url='http://gnupg.org/related_software/pinentry/'
arch=('i686' 'x86_64')
license=('GPL')
depends=('ncurses' 'libcap' 'libassuan' 'libsecret')
makedepends=('gtk2' 'qt5-base' 'gcr')
optdepends=('gtk2: gtk2 backend'
            'qt5-base: qt backend'
            'gcr: gnome3 backend')
source=("git+file:///home/adi/workspace/pinentry#branch=master")
sha1sums=('SKIP')

build() {
	cd "${srcdir}/${pkgname}"
	./autogen.sh
	./configure \
		--prefix=/usr \
		--enable-pinentry-tty \
		--enable-pinentry-curses \
		--enable-fallback-curses \
		--enable-pinentry-emacs \
		--enable-pinentry-gtk2 \
		--enable-pinentry-gnome3 \
		--enable-pinentry-qt \
		--enable-libsecret \
		--enable-maintainer-mode
	make
}

package() {
	cd "${srcdir}/${pkgname}"
	make DESTDIR="${pkgdir}" install
}
