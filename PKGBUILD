pkgname=libgee
pkgver=0.18.0
pkgrel=1
pkgdesc="GObject collection library"
url="http://live.gnome.org/Libgee"
license=(LGPL2.1)
arch=(x86_64)
depends=(glib2)
makedepends=(gobject-introspection vala python2)
source=(http://ftp.gnome.org/pub/GNOME/sources/$pkgname/${pkgver:0:4}/$pkgname-$pkgver.tar.xz)
sha256sums=('4ad99ef937d071b4883c061df40bfe233f7649d50c354cf81235f180b4244399')

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr --disable-static
  make
}

check() {
  cd $pkgname-$pkgver
  # generates a bazillion traps - make sure systemd's core_pattern
  # is deactivated, or you'll DoS the journal and the system
  #make check
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}
