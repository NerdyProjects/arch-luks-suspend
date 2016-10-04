_pkgname=arch-luks-suspend
pkgname=$_pkgname-git
pkgver=
pkgrel=1
pkgdesc="Lock encrypted root volume on suspend"
arch=('any')
url="https://github.com/NerdyProjects/arch-luks-suspend"
license=('GPL3')
depends=('systemd' 'cryptsetup' 'mkinitcpio')
makedepends=('git')
backup=('etc/systemd/system/systemd-suspend.service')
install=install
source=("git://github.com/NerdyProjects/$_pkgname.git")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$_pkgname"
  _date=$(git show -s --format='%ci' | cut -d' ' -f1 | sed 's/-//g')
  _hash=$(git show -s --format='%h')
  echo "$_date.g$_hash"
}

package() {
  cd "$srcdir/$_pkgname"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
