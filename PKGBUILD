# Contrinutor: Anton Leontiev <scileont /at/ gmail.com>
pkgname=gst-rtsp-server
pkgver=1.14.4
pkgrel=1
pkgdesc='RTSP server library based on GStreamer'
arch=('i686' 'x86_64' 'armv7h')
url='http://gstreamer.freedesktop.org/modules/gst-rtsp-server.html'
license=('LGPL')
depends=("gst-plugins-base>=$pkgver")
source=(http://gstreamer.freedesktop.org/src/$pkgname/$pkgname-$pkgver.tar.xz)
md5sums=('ab0fb5c829266a500e14b46b7bdf06bf')

build() {
	cd $pkgname-$pkgver
	./configure --prefix=/usr
	make
}

package() {
	cd $pkgname-$pkgver
	make install DESTDIR="$pkgdir"
	install -Dm755 examples/.libs/test-mp4 "$pkgdir/usr/bin/gst-rtsp-mp4"
	install -Dm755 examples/.libs/test-launch "$pkgdir/usr/bin/gst-rtsp-launch"
	install -Dm755 examples/.libs/test-netclock "$pkgdir/usr/bin/gst-rtsp-netclock"
	install -Dm755 examples/.libs/test-netclock-client "$pkgdir/usr/bin/gst-rtsp-netclock-client"
}
