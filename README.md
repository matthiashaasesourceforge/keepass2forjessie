# keepass2forjessie
keepass2forjessie


# tail -11 control
Description: Password manager
 repack on jessie without deps on libgcrypt20 (>= 1.8.0-0)
 with https://coderwall.com/p/hes3ha/change-the-dependencies-of-a-deb-package
 done by <matthias.haase.sourceforge@gmx.de>.
 KeePass is a easy-to-use password manager for Windows, Linux, Mac OS X and
 mobile devices. You can store your passwords in highly-encrypted databases,
 which can only be unlocked with one master password and/or a key file.
 A database consists of only one file that can be transferred from one computer
 to another easily.
 KeePass can import data from various file formats. The password list can be
 exported to various formats, including TXT, HTML, XML and CSV files.

# head -11 control
Package: keepass2
Version: 2.43+dfsg-1
Architecture: all
Maintainer: Debian CLI Applications Team <pkg-cli-apps-team@lists.alioth.debian.org>
Installed-Size: 3450
Depends: mono-runtime (>= 3.0~), libmono-corlib4.5-cil (>= 5.18.0.240), libmono-system-drawing4.0-cil (>= 5.12.0.309), libmono-system-security4.0-cil (>= 5.18.0.240), libmono-system-windows-forms4.0-cil (>= 5.16.0.220), libmono-system-xml4.0-cil (>= 4.6.1.3), libmono-system4.0-cil (>= 5.18.0.240), libx11-6 (>= 2:1.6.0)
Recommends: xsel
Suggests: keepass2-doc, mono-dmcs, xdotool
Section: utils
Priority: optional
Homepage: http://keepass.info/

# howto done:
read https://coderwall.com/p/hes3ha/change-the-dependencies-of-a-deb-package
download keepass2_2.43+dfsg-1_all.deb
ar x keepass2_2.43+dfsg-1_all.deb
tar -xf control.tar.xz
vi control
# remove "libgcrypt20 (>= 1.8.0-0)," per vi
mv control.tar.xz control.org.tar.xz
tar c md5sums control | xz > control.tar.xz
ar rcs keepass2_2.43+dfsg-1_all_without_dep_on_libgcrypt20.1.8.0-0.deb debian-binary control.tar.xz data.tar.xz
