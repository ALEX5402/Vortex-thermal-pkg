pkgbase=vortex-thermal

# Description of the package
pkgdesc='Vortex - Thermal'

gitgubrepo='Vortex-thermal'

# Version of the package
pkgver=1.0.3

groups=(vortex)
# Release number of the package
pkgrel=1

# Epoch, used for versioning in case of conflicts (default is 1)
epoch=1

conflicts=('cachyos-settings')

# Installation script
install=vortex-thermal.install

# Supported architectures
arch=('any')

# License type
license=('GPL-1.0-only')

# Build dependencies
makedepends=('coreutils')

# Runtime dependencies
depends=(
    'zram-generator'
    'ananicy-cpp'
    'cpupower'
    'inxi'
    'curl'
    'jq'
    'systemd>=256'
)

# Conflicts with these packages
conflicts=('cachyos-settings')


RELEASE_INFO=$(curl -L -H "Accept: application/vnd.github+json" "https://api.github.com/repos/alex5402/Vortex-thermal/releases/latest")


TAGNAME=$(echo "$RELEASE_INFO" | jq -r '.tag_name')
dirtyhash=$(echo "$RELEASE_INFO" | jq -r '.body')
SHA356HASH=$(echo -e "$dirtyhash" | sed 's/\\n//g')

options=('!strip')

# Optional dependencies with descriptions
optdepends=(
    'cachyos-ananicy-rules'
    'ruby: for tunecfs2'
    'libluv: for topmem'
    'lua-luv: for topmem'
    'irqbalance'
    'power-profiles-daemon: For game-performance'
)

source=("https://github.com/ALEX5402/Vortex-thermal/archive/refs/tags/$TAGNAME.tar.gz")
sha256sums=("${SHA356HASH}")

pkgname=$pkgbase

package() {
    install -d "${pkgdir}/usr"
    cp -rf "${srcdir}/${gitgubrepo}-${pkgver}/usr" "${pkgdir}"
}
