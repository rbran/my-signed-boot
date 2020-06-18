# Maintainer: me <me@rubens.io>
pkgname=my-signed-boot
pkgver=1.0
pkgrel=1
pkgdesc="My script to create a custom UEFI cert and sign the kernel stub"
arch=('any')
url="https://bitbucket.org/e760d50e/my-signed-boot"
license=('GPL3')
depends=('systemd' 'efitools' 'sbsigntools' 'util-linux')
source=(local://create-my-signed-boot-cert
	    local://kernel-command-line-old.txt
	    local://create-my-signed-boot-image
	    local://99-my-signed-boot.hook)
sha256sums=('39c10432d3377da0e31898d93a038a0c1f0d43b8cdd73048b1bd6b5bef98aaa3'
            'bba66c889f16e26304f591d4c203c4841cc81c14166c570a1abf7d5a0e6d30ed'
            '77561ea4707c33d7d942da18278726a48dfbfb4712f703305fe35ff51181905b'
            '07fc0e36848771204ec44ad3c976e4daaa77658793e9f77e035555f1d2817fce')

package() {
  cd "$srcdir/"
  mkdir -m700 -p "$pkgdir/etc/my-signed-boot"
  install -Dm755 "$srcdir/kernel-command-line-old.txt" "$pkgdir/etc/my-signed-boot/kernel-command-line-old.txt"
  install -Dm755 "$srcdir/create-my-signed-boot-cert" "$pkgdir/usr/bin/create-my-signed-boot-cert"
  install -Dm755 "$srcdir/create-my-signed-boot-image" "$pkgdir/usr/bin/create-my-signed-boot-image"
  install -Dm644 "$srcdir/99-my-signed-boot.hook" "$pkgdir/usr/share/libalpm/hooks/99-my-signed-boot.hook"
}
