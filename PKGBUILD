# Maintainer: Sam Burgos <santiago.burgos1089@gmail.com>
# Modified by Rafael from RebornOS

pkgname=mintstick
pkgver=1.4.6
pkgrel=1.1
pkgdesc='A GUI to write .img or .iso files to a USB Key. It can also format them'
arch=('any')
url="http://packages.linuxmint.com/pool/main/m/${pkgname}"
license=(GPL)
depends=(coreutils desktop-file-utils dosfstools e2fsprogs exfat-utils glib2 gtk3
         ntfs-3g parted polkit procps-ng python python-dbus python-gobject
         python-pyparted python-xapp udisks2 util-linux xapps)
makedepends=(gettext)
conflicts=(mintstick-git)
source=("${pkgname}-${pkgver}.tar.xz::${url}/${pkgname}_${pkgver}.tar.xz"
        "${pkgname}.svg" "${pkgname}.desktop" "${pkgname}-format.desktop"
        "${pkgname}-format-kde.desktop" "${pkgname}-kde.desktop")
        
sha256sums=('586e38dfb2c607c610043c0d66a9bdf3c559736a351a7d8dff64caf6359d1c92'
            '48d8ef1370a2c249ea0f848ae289c5948e3b6e490fc07623cb02bbeb493f6e7e'
            '6b540ead90133d26e33bb2f3588f25dcd24dc5f537155f6d8462d4d5cc8ba608'
            '76bed23109109dbe6cbb792be41aefa77ec4c13974ba4fc7ffc7752b13c0d12e'
            'c2a55243798466af06acaa6222ed4183589854679dab296642c1eff5206fb58d'
            'a4bbfebec10eb8fb510e08139b7e1bf7a5ed42009ac608a0cf21480a9487e4a8')

package() {
    mkdir -p ${pkgdir}/usr/bin
    mkdir -p ${pkgdir}/usr/share/applications
    mkdir -p ${pkgdir}/usr/share/polkit-1/actions
    mkdir -p ${pkgdir}/usr/lib/${pkgname}
    mkdir -p ${pkgdir}/usr/share/${pkgname}
    mkdir -p ${pkgdir}/usr/share/icons
    cp ${pkgname}.svg ${pkgdir}/usr/share/icons
    cp -rp ${srcdir}/${pkgname}/share/nemo ${pkgdir}/usr/share
    install -D -m 644 ${pkgname}.desktop ${pkgdir}/usr/share/applications/
    install -D -m 644 ${pkgname}-format.desktop ${pkgdir}/usr/share/applications/
    install -D -m 644 ${pkgname}-kde.desktop ${pkgdir}/usr/share/applications/
    install -D -m 644 ${pkgname}-format-kde.desktop ${pkgdir}/usr/share/applications/
    cp ${srcdir}/${pkgname}/share/polkit/com.linuxmint.mintstick.policy ${pkgdir}/usr/share/polkit-1/actions
    cp -r ${srcdir}/${pkgname}/lib/* ${pkgdir}/usr/lib/${pkgname}
    cp -r ${srcdir}/${pkgname}/share/${pkgname}/* ${pkgdir}/usr/share/${pkgname}
    install -D -m 755 ${srcdir}/${pkgname}/${pkgname} ${pkgdir}/usr/bin/
}
