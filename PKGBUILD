# Maintainer: Padraic Fanning < fanninpm AT miamioh DOT edu >
# Contributor: Jake <aur@ja-ke.tech>
# Contributor: Ian MacKay <immackay0@gmail.com>

_pkgname='github-desktop'
pkgname="${_pkgname}-bin"
pkgver=3.4.5_linux1
pkgrel=1
_pkgver="${pkgver//_/-}"
_gitname="release-${_pkgver}"
pkgdesc="GUI for managing Git and GitHub."
arch=('x86_64' 'aarch64' 'armv7h')
url="https://desktop.github.com"
license=('MIT')
depends=(
    'curl'
    'git'
    'libsecret'
    'libxss'
    'nspr'
    'nss'
    'org.freedesktop.secrets'
    'unzip'
)
optdepends=('hub: CLI interface for GitHub.')
provides=(${_pkgname})
conflicts=(${_pkgname})
source=(${_pkgname}.desktop)
source_x86_64=(https://github.com/shiftkey/desktop/releases/download/${_gitname}/GitHubDesktop-linux-amd64-${_pkgver}.deb)
source_aarch64=(https://github.com/shiftkey/desktop/releases/download/${_gitname}/GitHubDesktop-linux-arm64-${_pkgver}.deb)
source_armv7h=(https://github.com/shiftkey/desktop/releases/download/${_gitname}/GitHubDesktop-linux-armhf-${_pkgver}.deb)
sha256sums=('932e4c456e8c6db03d27172cf0daa37806bf025bb560d8b3d758c0997d1a618c')
sha256sums_x86_64=('5a4fd715463771dc491eb2069eb87de18ab219a74d31db74c1efa91d9858d297')
sha256sums_aarch64=('1a0c1aefc89490cb9d9cd0d635f2afb60aade77101436dd54a60495e37090dd2')
sha256sums_armv7h=('a5d31ce0a49bb5399275f0e023763f0896f346fcfab72f7bbe85e7c96c87d924')
package() {
    tar xf data.tar.xz -C "${pkgdir}"
    install -d "${pkgdir}/opt/${_pkgname}"
    mv "${pkgdir}/usr/lib/github-desktop" "${pkgdir}/opt/"

    rm "${pkgdir}/usr/share/applications/github-desktop.desktop"
    install -Dm644 "${_pkgname}.desktop" "${pkgdir}/usr/share/applications/${_pkgname}.desktop"

    ln -sf "/opt/$_pkgname/$_pkgname" "${pkgdir}/usr/bin/$_pkgname"
}
