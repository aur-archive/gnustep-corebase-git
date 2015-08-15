# Maintainer : ziggi <xziggix@gmail.com>
pkgname='gnustep-corebase-git'
pkgver=20130129
pkgrel=1
pkgdesc='The GNUstep CoreBase Library is a library of general-purpose, non-graphical C objects.'
arch=('i686' 'x86_64')
url='http://savannah.gnu.org/bugs/?group=gnustep'
license=('LGPL')
makedepends=('gnustep-make')
provides=('gnustep-corebase')

_gitroot='git://github.com/gnustep/gnustep-corebase.git'
_gitname='gnustep-corebase'

build () {
	cd "${srcdir}"
	if [ -d "${_gitname}" ] ; then
		msg "The files are updated"
	else
		git clone "${_gitroot}"
	fi
	cd "${_gitname}"
	./configure
	make
}

package() {
	cd "${_gitname}"
	make DESTDIR="$pkgdir" install
}
