# lib7zip
*Automatically exported from code.google.com/p/lib7zip*

A library using 7z.dll/7z.so(from 7-Zip) to handle different archive types. 
lib7zip is based on 7zip/p7zip source code, but NOT including any source code from 7zip/p7zip.
## Tips
+ Build lib7zip
  + Under UNIX/LINUX like system
    1. Get a copy of p7zip source code, and extract to a folder
    2. Define a env P7ZIP_SOURCE_DIR point to the extracted folder
    3. Call configure && make to build lib7zip library, or call autogen.sh
  + Under windows
    1. Get mingw from http://www.mingw.org
    2. Get a copy of original 7zip source code, NOT the p7zip for linux
    3. Define a env P7ZIP_SOURCE_DIR point to the extracted folder
    4. Call configure && make to build lib7zip library, or call autogen.sh
+ Run lib7zip
  + Under UNIX/LINUX like system
    1. install p7zip binary
    2. find 7z.so path, export LD_LIBRARY_PATH=&lt;where 7z.so existing&gt;
  + Under Windows
    1. install 7zip binary
    2. copy 7z.dll to where your application existing
  
> Any time or any problem about lib7zip, please feel free to write me an email.
Any feature or patch request, please also feel free to write me an email.

## Thanks
+ Many thanks to Joe who provide so many great patches
+ Many thanks to Christoph who give so many great advises and patch.
+ Many thanks to Christoph Thielecke to provide great patches for OS2 and dynamic library

## To Do
+ Add Compress function to library

## Related Projects
+ Python Binding created by Mark, http://github.com/harvimt/pylib7zip

## Change Log
### 1.6.5
+ Add new parameter bool fDetectFileTypeBySignature to `OpenArchive`, when fDetectFileTypeBySignature = true, lib7zip will using file signature instead file name extension to detect file type
+ remove out-of-dated visual studio files

### 1.6.4
+ add AUTHORS COPYING file
+ add `LIB7ZIP_` prefix to error code enum,break the old client, please update your code
+ add APIs `SetLib7ZipLocale` and `GetLib7ZipLocale`, client could use these API to force lib7zip locale, otherwise lib7zip will use current user's locale
+ add list of path to find 7z.so when 7z.so is not in users ld path
+ fix Mac OSX compile fail problem

### 1.6.3
+ Add `GetLastError` to `C7ZipLibrary` and Error code define in lib7zip.h
+ open archive with password now work for archive created by 7za a -mhe -p, who encrypted the file names in archive

### 1.6.2
+ Fixed broken windows built system
+ Fixed build script for windows

### 1.6.1
+ Add OS2 support
+ create dynamic library along with static library

### 1.6.0
+ Add Multi-Volume support

### 1.5.0
+ Add Password support

### 1.4.1
+ Add GetProperty functions to C7ZipArchive to retrieve archive properties
+ Add kpidSize to return Item umcompressed size, the same as GetSize returning

### 1.4.0
+ Add patches from Christoph
  1. make the test program works when no Test7Zip.7z found
+ Add functions to get more property about items in the archive
+ Tested on Mac OS X
+ Move source control to [Mercurial](http://mercurial.selenic.com/) for better distributed development

### 1.3.0
+ Add patches from Joe,
  1. make the library work with latest p7zip 9.20

### 1.0.2
+ Add patches from Joe,
  1. Add a method to get the compressed size
  1. Add a method to expose whether the file is encrypted
+ Build scripts update
+ Small fix to make the lib working with the latest p7zip source

### 1.0.1
+ First release, support both LINUX and windows platform.
