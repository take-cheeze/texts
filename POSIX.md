## dirent
* [Document](http://pubs.opengroup.org/onlinepubs/007908799/xsh/dirent.h.html)
* [Windows implementation](http://www.softagalleria.net/dirent.php)

## realpath
* [man page](http://linuxjm.sourceforge.jp/html/LDP_man-pages/man3/realpath.3.html)
* [macro in mingw](http://sourceforge.net/p/mingw/patches/256/)
* [C++ implementation](http://insanecoding.blogspot.jp/2007/11/implementing-realpath-in-c.html)
* Windows
  * [getting all drive letters](http://stackoverflow.com/questions/286534/enumerating-all-available-drive-letters-in-windows)
  * [GetLogicalDriveStrings](http://msdn.microsoft.com/en-us/library/aa364975(VS.85).aspx)
    * use to get drive names
  * [GetVolumeInformation](http://msdn.microsoft.com/en-us/library/aa364993(v=vs.85).aspx)
    * use to get volume name
  * [_fullpath/_wfullpath](http://msdn.microsoft.com/ja-jp/library/506720ff)
    * equivalent to realpath()
  * [Application Registration](http://msdn.microsoft.com/en-us/library/windows/desktop/ee872121(v=vs.85).aspx)
    * how to get path of application executable

## basename/dirname
* [man page](http://linuxjm.sourceforge.jp/html/LDP_man-pages/man3/basename.3.html)
* basename gets filename from path
* dirname gets directory from path
* path = dirname + PATH_SEPARATOR + basename
* [glic implementation](http://repo.or.cz/w/glibc.git/blob?f=misc/dirname.c)