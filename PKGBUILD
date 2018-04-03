# Maintainer: Eric Vidal <eric@obarun.org>
# based on the original https://git.archlinux.org/svntogit/community.git/log/trunk?h=packages/udevil
# 						Maintainer: Alad Wenter <alad@mailbox.org>
# 						Contributor:  Bartłomiej Piotrowski <nospam@bpiotrowski.pl>
# 						Contributor: IgnorantGuru http://igurublog.wordpress.com/contact-ignorantguru/

pkgname=udevil
pkgver=0.4.4
pkgrel=3
_commit=77a61806fadbf19f02072df1aa67191fc375c35d
arch=('x86_64')
pkgdesc='Mount and unmount without password'
url='http://ignorantguru.github.com/udevil/'
license=('GPL3')
makedepends=('intltool' 'gettext' 'git')
depends=('udev' 'glib2')
optdepends=('davfs2:     mount WebDAV shares'
            'nfs-utils:  mount nfs shares'
            'sshfs:      mount sftp shares'
            'curlftpfs:  mount ftp shares'
            'cifs-utils: mount samba shares'
            'zenity:     devmon popups'
            'udisks2:    devmon mount without suid udevil')
provides=('devmon')
backup=('etc/udevil/udevil.conf' 'etc/conf.d/devmon')
install=$pkgname.install
source=("$pkgname-$pkgver::git+https://github.com/IgnorantGuru/udevil.git#commit=$_commit")
sha256sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

build() {
    cd "$pkgname-$pkgver"
    ./configure --prefix=/usr
    make
}

package() {
    cd "$pkgname-$pkgver"
    make DESTDIR="$pkgdir" install
}
