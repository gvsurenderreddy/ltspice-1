# Maintainer: Max Stabel <max dot stabel03 at gmail dot com>

pkgname=ltspice
pkgver=4.23b
pkgrel=1
pkgdesc="SPICE simulator, schematic capture and waveform viewer of electronic circuits for windows."
arch=('i686' 'x86_64')
url="http://www.linear.com/"
license=('custom')
depends=('wine')
makedepends=('git')
source=("$pkgname::git+https://github.com/M4a1x/$pkgname.git#branch=$pkgver"
        "$pkgname.sh")
md5sums=('SKIP'
        'e4201f86691af79e7312f22a3fa2a2f1')
#install=ltspice.install

package()
{
    # Install License
    install -D -m644 "$srcdir/$pkgname/License.txt" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    rm -f "$srcdir/$pkgname/License.txt"

    # Install binary files to /opt
    mkdir -p "$pkgdir/opt/$pkgname"
    cp -r "$srcdir/$pkgname" "$pkgdir/opt/$pkgdir"
    chmod 755 -R "$pkgdir/opt/$pkgdir"

    #Install /usr/bin startscript
    install -Dm755 "$pkgname.sh" "$pkgdir/usr/bin/$pkgname"
    install -Dm755 "$pkgname-help.sh" "$pkgdir/usr/bin/$pkgname-help"
}