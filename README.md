# hjonkcli
read the sidebar bleh

![demo screenshot](./assets/hjonkclidemo.png)

***i do not have a windows version, please use WSL2 if you need windows support***

# installation
dependencies: ```gcc, pkgconf/pkg-config, libcurl, libcjson```
on arch? use the aur
```git clone https://aur.archlinux.org/hjonkcli.git && cd hjonkcli
makepkg -si
```
or your favorite aur helper  
elsewhere? build manually
```git clone https://github.com/asticassiasuletta/hjonkcli && cd hjonkcli
gcc hjonk.c -libcurl -libcjson -o hjonkcli
(sudo) mv hjonkcli /local/usr/bin/hjonkcli
```

on windows? download from winget when it's setup
```winget install suletta.hjonkcli```
or build it yourself using mingw64, dependencies:
```mingw-w64-x86_64-gcc mingw-w64-x86_64-curl-winssl mingw-w64-x86_64-cjson```
build:
```gcc hjonk.c -static -lcurl -lcjson -lws2_32 -lwldap32 -lcrypt32 -lbcrypt -o hjonk.exe```
doesn't work? figure it out yourself i'm too tired for this shit
# usage
run ```hjonkcli``` for instructions but the tl:dr is
make a new api key
run ```hjonkcli auth YOUR_API_KEY```
profit
