# Maintainer: Padraic Fanning < fanninpm AT miamioh DOT edu >
# Contributor: Jake <aur@ja-ke.tech>
# Contributor: Ian MacKay <immackay0@gmail.com>

_pkgname='github-desktop'
pkgname="${_pkgname}-bin"
pkgver=3.3.13_linux1
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
sha256sums_x86_64=('1c6c28235e8601b19f1723495a90295b2a9a61de90aa1ea7b6c466c2651f1c63')
sha256sums_aarch64=('6bd27583365ceaea41de0c474fcda4d3349bc6728f21aae391cbb124b5fda8f8')
sha256sums_armv7h=('73df6f770ddae319364e95ffb84b2bb2be1d4f1f0571d1b3a97109ef555800e6')
package() {
    tar xf data.tar.xz -C "${pkgdir}"
    install -d "${pkgdir}/opt/${_pkgname}"
    mv "${pkgdir}/usr/lib/github-desktop" "${pkgdir}/opt/"

    rm "${pkgdir}/usr/share/applications/github-desktop.desktop"
    install -Dm644 "${_pkgname}.desktop" "${pkgdir}/usr/share/applications/${_pkgname}.desktop"

    ln -sf "/opt/$_pkgname/$_pkgname" "${pkgdir}/usr/bin/$_pkgname"
}
