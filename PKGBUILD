# Maintainer: speps <speps at aur dot archlinux dot org>

_uname=lyricat
_commit=e0c78bf
pkgname=hotot-qt
pkgver=0.9.8.13
pkgrel=1
pkgdesc="A lightweight & open source microblogging software (twitter identi.ca). Qt4 frontend."
arch=('i686' 'x86_64')
url="http://www.hotot.org/"
license=('LGPL3')
depends=('hotot-data' 'qtwebkit')
makedepends=('cmake' 'intltool' 'python2')
install="hotot-qt.install"
source=("https://github.com/$_uname/Hotot/tarball/$_commit")
md5sums=('6121926b8947c4093beb2ed79f10e855')

build() {
  cd ${srcdir}/$_uname-Hotot-*
  [ -d bld ] || mkdir bld && cd bld
  cmake .. -DCMAKE_INSTALL_PREFIX=/usr \
           -DWITH_GTK=OFF \
           -DWITH_GTK2=OFF \
           -DWITH_GTK3=OFF \
           -DWITH_QT=ON \
           -DWITH_QT5=OFF \
           -DWITH_CHROME=OFF \
           -DPYTHON_EXECUTABLE=/usr/bin/python2
  make
}

package() {
  cd ${srcdir}/$_uname-Hotot-*/bld/qt
  DESTDIR="$pkgdir/" cmake -P cmake_install.cmake
}

# vim:set ts=2 sw=2 et:
