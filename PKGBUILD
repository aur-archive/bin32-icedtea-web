# Maintainer: c0nd0r <gcesarmza@gmail.com>
pkgname=bin32-icedtea-web
pkgver=1.3.1
pkgrel=1
srcpkgrel=1
pkgdesc="Provides a Free Software 32-bit web browser plugin running applets written in the Java programming language and an implementation of Java Web Start, originally based on the NetX project, for Arch x86_64"
arch=('x86_64')
license=('custom')
url="http://www.java.net"
depends=('bin32-openjdk6' 'lib32-gtk2' )
#Replace this with the mirror you prefer
mirror="http://mirrors.kernel.org/archlinux" 
source=(${mirror}/extra/os/i686/${pkgname:6}-$pkgver-$srcpkgrel-i686.pkg.tar.xz)

md5sums=('4188d5fa63c9f219b298c0cb1cb77a62')

build() {
  cd ${startdir}/src
  mv usr $pkgdir
  cd $pkgdir/usr
  mv lib lib32
  rm -rf bin
  rm -rf lib32/mozilla
  rm -rf share
  cd lib32/jvm/java-6-openjdk/jre/bin
  rm *
  ln -s ../../bin/itweb-settings
  ln -s ../../bin/javaws
  mkdir -p $pkgdir/opt/mozilla/lib/plugins
  cd $pkgdir/opt/mozilla/lib/plugins
  ln -s ../../../../usr/lib32/jvm/java-6-openjdk/lib/IcedTeaPlugin.so
  cd $pkgdir/usr/lib32/jvm/java-6-openjdk/bin
  sed 's/\/usr\/lib\/jvm/\/usr\/lib32\/jvm/g' -i itweb-settings
  sed 's/\/usr\/lib\/jvm/\/usr\/lib32\/jvm/g' -i javaws
}

