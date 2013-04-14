pkgname=brscan-skey
pkgver=0.2.4_0
pkgrel=1
pkgdesc="Brother Scan-Key-Tool"
depends=('sane' 'sed')
arch=('i686' 'x86_64')
url="http://welcome.solutions.brother.com/bsc/public_s/id/linux/en/index.html"
license=("GPL" 'custom:brother commercial license')
install=brscan-skey.install

if [ $(uname -m) = "x86_64" ]; then
  deb="${pkgname}-${pkgver/_/-}.x86_64.rpm"
  deb_md5sum="494f7256c8e0ee643157e7dba58ff6d4"
else
  deb="${pkgname}-${pkgver/_/-}.i386.rpm"
  deb_md5sum="f6ac581adc9cab92551a0aa17508ab62"
fi

source=("http://pub.brother.com/pub/com/bsc/linux/dlf/$deb")
md5sums=($deb_md5sum) 

build() {
	mkdir -p $srcdir/usr/bin
    if [[ ! -L "$srcdir"/usr/bin/brscan-skey ]]; then
        ln -s /opt/brother/scanner/brscan-skey/brscan-skey "$srcdir"/usr/bin/brscan-skey
    fi
}

package() {
    cp -R "$srcdir"/{opt,usr} "$pkgdir"
}
