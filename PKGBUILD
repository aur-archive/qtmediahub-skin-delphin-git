pkgname=qtmediahub-skin-delphin-git
pkgver=20110916
pkgrel=1
pkgdesc='Delphin skin for qtmediahub'
arch=('i686' 'x86_64')
url='http://www.qtmediahub.com'
license=('BSD')
depends=('qtmediahub-core-git')
source=()
md5sums=()

_gitroot="git://gitorious.org/qtmediahub/delphin.git"
_gitname="delphin"

build() {
    msg "Connecting to GIT server...."

    if [ -d "$srcdir/$_gitname" ] ; then
        cd $_gitname && git pull origin
        msg "The local files are updated."
    else
        git clone --depth=1 $_gitroot
    fi

    msg "GIT checkout done or server timeout"

    cd "$srcdir/$_gitname"
}

package() {
    cd "${srcdir}/$_gitname"
 
    mkdir -p ${pkgdir}/usr/share/qtmediahub/skins/delphin/
    cp -arf * ${pkgdir}/usr/share/qtmediahub/skins/delphin/
}
