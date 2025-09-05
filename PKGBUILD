pkgname=vala
pkgver=0.56.18
pkgrel=1
pkgdesc="Compiler for the GObject type system"
arch=('x86_64')
url="https://wiki.gnome.org/Projects/Vala"
license=('LGPL-2.1-or-later')
depends=(
    'bash'
    'dejavu-fonts-ttf'
    'gcc'
    'glib2'
    'glibc'
    'pkgconf'

)
makedepends=(
    'dbus'
    'gobject-introspection'
    'help2man'
    'libxslt'
)
source=(https://download.gnome.org/sources/vala/${pkgver%.*}/${pkgname}-${pkgver}.tar.xz)
sha256sums=(f2affe7d40ab63db8e7b9ecc3f6bdc9c2fc7e3134c84ff2d795f482fe926a382)

build() {
    cd ${pkgname}-${pkgver}

    local configure_args=(
        --disable-valadoc
        ${configure_options}
    )

    ./configure "${configure_args[@]}"

    make
}

package() {
    cd ${pkgname}-${pkgver}

    make DESTDIR=${pkgdir} install
}
