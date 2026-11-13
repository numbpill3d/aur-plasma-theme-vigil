# Maintainer: numbpill3d <void@nothing>
# Contributor: numbpill3d <void@nothing>
pkgname=plasma-theme-vigil
pkgname+=(sddm-theme-vigil)
pkgname+=(plymouth-theme-vigil)
pkgver=1.0
pkgrel=1
pkgdesc='Minimal animated ASCII/TUI alien-Daedric suite for KDE Plasma 6 by splicer scorn (voidrane)'
arch=('any')
url='https://github.com/numbpill3d/vigil'
license=('GPL-3.0-or-later')
depends=('plasma-workspace')
optdepends=(
  'sddm: SDDM login theme'
  'plymouth: Plymouth boot splash'
)
source=("$pkgname-$pkgver.tar.gz::https://github.com/numbpill3d/vigil/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('SKIP')

package_plasma-theme-vigil() {
  cd "$srcdir/vigil-$pkgver"

  # Global theme: look-and-feel + KSplash
  install -d "$pkgdir/usr/share/plasma/look-and-feel"
  cp -r lookandfeel/scorn.vigil "$pkgdir/usr/share/plasma/look-and-feel/"

  # Animated wallpaper (desktop and lock screen)
  install -d "$pkgdir/usr/share/plasma/wallpapers"
  cp -r wallpaper/scorn.vigil "$pkgdir/usr/share/plasma/wallpapers/"

  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

package_sddm-theme-vigil() {
  depends=('sddm')
  optdepends=('plasma-theme-vigil: the Plasma 6 half of the suite')
  pkgdesc='SDDM login theme — animated ASCII/TUI alien-Daedric suite'
  cd "$srcdir/vigil-$pkgver"

  install -d "$pkgdir/usr/share/sddm/themes"
  cp -r sddm/vigil "$pkgdir/usr/share/sddm/themes/"

  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

package_plymouth-theme-vigil() {
  depends=('plymouth')
  optdepends=('plasma-theme-vigil: the Plasma 6 half of the suite')
  pkgdesc='Plymouth boot splash — animated ASCII/TUI alien-Daedric suite'
  cd "$srcdir/vigil-$pkgver"

  install -d "$pkgdir/usr/share/plymouth/themes"
  cp -r plymouth/vigil "$pkgdir/usr/share/plymouth/themes/"

  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
