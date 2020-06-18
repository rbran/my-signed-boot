# Maintainer: me <me@rubens.io>
pkgname=my-signed-boot
pkgver=1.0
pkgrel=1
pkgdesc="My script to create a custom UEFI cert and sign the kernel stub"
arch=('any')
url="https://bitbucket.org/e760d50e/my-signed-boot"
license=('GPL3')
depends=('systemd' 'efitools' 'sbsigntools' 'util-linux')
source=('local://create-my-signed-boot-cert'
        'local://kernel-command-line-old.txt'
        'local://create-my-signed-boot-image'
        'local://99-my-signed-boot.hook')
sha256sums=('cc633f26482422277797d24b04b3d287db65cb1252671b0c86a42f15e5eed7b5'
            '97afcfb8c02c2a3a3fc26c840501e61b503a7b97b2b21765696d65c6f154df2a'
            '3539f4122de1e081e844fbb6ac21b4ef1dd416775d6b8105395ea5d1a2b91bf4'
            '4ac82b8b55662f1067b74d72ea7080b8a116a912c08d84e98a6f555cdd3c239c')

package() {
  cd "$srcdir/"
  mkdir -m700 -p "$pkgdir/etc/my-signed-boot"
  install -Dm755 "$srcdir/kernel-command-line-old.txt" "$pkgdir/etc/my-signed-boot/kernel-command-line-old.txt"
  install -Dm755 "$srcdir/create-my-signed-boot-cert" "$pkgdir/usr/bin/create-my-signed-boot-cert"
  install -Dm755 "$srcdir/create-my-signed-boot-image" "$pkgdir/usr/bin/create-my-signed-boot-image"
  install -Dm644 "$srcdir/99-my-signed-boot.hook" "$pkgdir/usr/share/libalpm/hooks/99-my-signed-boot.hook"
}
