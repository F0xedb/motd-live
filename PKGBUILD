# Maintainer: Tom Meyers tom@odex.be
pkgname=motd-live
pkgver=r6.92ae6ec
pkgrel=1
pkgdesc="Dynamically update your motd when logging in over ssh"
arch=(any)
url="https://github.com/F0xedb/motd-live"
_reponame="motd-live"
license=('MIT')

source=(
"git+https://github.com/F0xedb/motd-live.git")
md5sums=('SKIP')
depends=('bash' 'cronie')
makedepends=('git')

pkgver() {
  cd "$srcdir/$_reponame"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}


build() {
    return 0;
}

package() {
        cd "$srcdir/$_reponame"
        # install common packages
        install -Dm644 motd "$pkgdir"/etc/cron.d/motd
        install -Dm755 motd-live-cm "$pkgdir"/usr/bin/motd-live


        # copy subdir from rofi
        mkdir -p "$pkgdir"/etc/motd-live/scripts
        cp 10-column-layout "$pkgdir"/etc/motd-live/10-column-layout
        cp 92-unattended-upgrades "$pkgdir"/etc/motd-live/92-unattended-upgrades

        for file in scripts/* ; do
            install -Dm755 "$file" "$pkgdir"/etc/motd-live/"$file"
        done
}
