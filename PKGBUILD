# Maintainer: WorMzy Tykashi <wormzy.tykashi@gmail.com>
pkgname=dream-svn
_svnroot=${pkgname%-svn}
pkgver=927
pkgrel=1
pkgdesc="A DRM (Digital Radio Mondiale) Reciever"
arch=('x86_64')
url="http://sourceforge.net/apps/mediawiki/drm/index.php?title=Main_Page"
license=('GPL')
depends=('qt5-svg' 'qt5-webkit' 'qwt-qt5' 'fftw' 'libpulse' 'speex' 'opus' 'libpcap' 'libusbx' 'libnl' 'libdbus')
makedepends=('subversion')
options=(!strip)
source=(svn+"http://svn.code.sf.net/p/drm/code/dream")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$_svnroot"
  svnversion
}

build() {
  cd "$srcdir/$_svnroot"
  qmake dream.pro QT_VERSION=5
  make
}

package() {
  cd "$srcdir/$_svnroot"
  make INSTALL_ROOT="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
