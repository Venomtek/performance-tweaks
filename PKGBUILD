# Maintainer: Librewish <librewish@gmail.com>


pkgbase=performance-tweaks
_gitname=performance-tweaks
pkgname=(
    'performance-tweaks'
    )
pkgver=0.0.1.r0.ge9d8ab2
pkgrel=1
arch=('any')
_branch='master'
url="https://gitlab.com/garuda-linux/themes-and-settings/settings/performance-tweaks"
license=('GPL')
makedepends=('git')
source=("git+$url.git#branch=${_branch}")
sha256sums=('SKIP')

_install() {
    if [[ -d $srcdir/$_gitname/$1/etc ]]; then
        install -d $pkgdir/etc
        cp -rf $srcdir/$_gitname/$1/etc $pkgdir
    fi

    if [[ -d $srcdir/$_gitname/$1/usr ]]; then
        install -d $pkgdir/etc
        cp -rf $srcdir/$_gitname/$1/usr $pkgdir
    fi
    
    if [[ -d $srcdir/$_gitname/$1/skel ]]; then
        install -d $pkgdir/etc
        cp -rf $srcdir/$_gitname/$1/skel $pkgdir/etc
    fi

}

pkgver() {
  cd $pkgname
  git describe --long | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

package_performance-tweaks() {
    pkgdesc='automatic tweaks for Improving performance while gaming and other tasks'
    depends=(
    'haveged'
    'irqbalance'
    'systemd-swap'   
	'hdparm'
    'thermald'
    'nohang-git'
    'prelockd-git'
    'memavaild-git'
	'ananicy-git'
    'auto-cpufreq-git'
    'profile-sync-daemon'
        )
    optdepends=(
        'timeshift-autosnap: for snapshots bfore pacman upgrade'
        'grub-btrfs: for grub entries to btrfs snapshots'
	'systemd-guest-user: for guest user support'
        )    
    install=performance-tweaks.install
    provides=('performance-tweaks')
    conflicts=('performance-tweaks' 'tlp')

    _install ''
}

