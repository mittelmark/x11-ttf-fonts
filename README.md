# x11-ttf-fonts

[![license](https://img.shields.io/badge/license-MIT-lightgray.svg)](https://opensource.org/license/MIT)
[![Release](https://img.shields.io/github/v/release/mittelmark/x11-ttf-fonts.svg?label=current+release)](https://github.com/mittelmark/x11-ttf-fonts/releases)
![Downloads](https://img.shields.io/github/downloads/mittelmark/x11-ttf-fonts/total)
![Commits](https://img.shields.io/github/commits-since/mittelmark/x11-ttf-fonts/latest)

## NAME

__x11-ttf-fonts-install__ - indexes a set of exiting monospaced fonts into ~/.local/share/fonts  
__x11-ttf-fonts-anonymous-pro__  - downloads and indexes the Anonymous Pro fonts into ~/.local/share/fonts  
__x11-ttf-fonts-courier-prime__  - downloads and indexes the Courier Prime fonts into ~/.local/share/fonts  
__x11-ttf-fonts-dejavu-sans-mono__  - downloads and indexes the Dejavu Sans Mono fonts into ~/.local/share/fonts  
__x11-ttf-fonts-source-code-pro__  - downloads and indexes the Adobe Source Code Pro fonts into ~/.local/share/fonts  
__x11-ttf-fonts-ubuntu__  - downloads and indexes the Ubuntu Mono fonts into ~/.local/share/fonts  



## SYNOPSIS

Platform Linux with X11 or Cygwin Windows with X11:

```
curl -fsSL https://github.com/mittelmark/x11-ttf-fonts/releases/latest/download/x11-ttf-fonts-install | bash
curl -fsSL https://github.com/mittelmark/x11-ttf-fonts/releases/latest/download/x11-ttf-fonts-anonymous-pro | bash
curl -fsSL https://github.com/mittelmark/x11-ttf-fonts/releases/latest/download/x11-ttf-fonts-courier-prime | bash
curl -fsSL https://github.com/mittelmark/x11-ttf-fonts/releases/latest/download/x11-ttf-fonts-dejavu-sans-mono | bash
curl -fsSL https://github.com/mittelmark/x11-ttf-fonts/releases/latest/download/x11-ttf-fonts-source-code-pro | bash
curl -fsSL https://github.com/mittelmark/x11-ttf-fonts/releases/latest/download/x11-ttf-fonts-ubuntu | bash 
```

## DESCRIPTION

Installs and/or indexes a set of monospaced true type fonts usuable for older X11 applications like the 
[Jasspa MicroEmacs](https://github.com/bjasspa/jasspa) text editor. TrueType fonts already installed on the current
machine are linked into `~/.local/share/fonts` using the `x11-ttf-fonts-install` script. Other fonts like:

- [Anonymous Pro](https://fonts.google.com/specimen/Anonymous+Pro)
- [Courier Prime](https://github.com/quoteunquoteapps/CourierPrime/)
- [Dejavu Sans Mono](https://github.com/go-fonts/dejavu)
- [Adobe Source Code Pro](https://github.com/adobe-fonts/source-code-pro/)
- [Ubuntu Mono](https://fonts.google.com/specimen/Ubuntu+Mono)

can be as well installed if the package manager does not support installing them using their own little shell scripts
as can be seen in the SYNOPSIS section.

## REQUIREMENTS

- Linux OS with X11 or XWayland
- MacOS with XQuartz (untested)
- Windows with Cygwin-X11 (untested)
- mkfontscale for font indexing

## LOCAL INSTALL

If you  just  like to link and  index  your  local  True  Type  fonts  without
executing  code  from  the web,  just  copy the code  below,  which is a short
version of the install script, into a running Bash session:


```bash
if [ ! -d ~/.local/share/fonts ] ; then
    echo "creating directory ~/.local/share/fonts"
    mkdir -p ~/.local/share/fonts
fi

find  /usr/ -iregex \
   ".*\\(Mono\\|Mono-?Bold\\|Mono-?Regular\\|Code-Regular\\|Code-Bold\\).ttf" 2>/dev/null \
| xargs ln -sf -t ~/.local/share/fonts/

mkfontscale ~/.local/share/fonts/
mkfontdir ~/.local/share/fonts/
res=$(xset q | grep -A 1 fontpath | grep .local/share/fonts)
if [[ "$res" == "" ]]; then
    xset +fp ~/.local/share/fonts/
fi
xset fp rehash
```

The updated font path  settings  using the `xset` command at the end should be
made permanent, how depends on your desktop and Window manager.

## LINKS

- [FreeBSD handbook on X11 fonts](https://docs.freebsd.org/en/books/handbook/x11/#x-fonts)
- [https://github.com/ProgrammingFonts/ProgrammingFonts](https://github.com/ProgrammingFonts/ProgrammingFonts)
- [https://github.com/braver/programmingfonts](https://github.com/braver/programmingfonts)
- [https://www.programmingfonts.org/ - Preview](https://www.programmingfonts.org/)

## SUPPORT

In case of problems, install suggestions for MacOS with XQuartz or suggestions for supporting other
fonts use the [Issues link](https://github.com/mittelmark/x11-ttf-fonts/issues) at the Github project page.

## AUTHOR and COPYRIGHT

@ Detlef Groth, University of Potsdam, Germany, 2024

## LICENSE

The install scripts are licensed under the MIT license, the fonts comes with their own license which,
in case you use the download scripts is as well downloaded in parallel to the ttf files.

Here the links to the font licenses of 
[Anonymous Pro](https://github.com/braver/programmingfonts/raw/gh-pages/fonts/resources/anonymous-pro/license.txt),
[Courier Prime](https://github.com/quoteunquoteapps/CourierPrime/blob/master/OFL.txt),
[Dejavu Sans Mono](https://github.com/go-fonts/dejavu/raw/main/LICENSE-DejaVu),
[Adobe Source Code Pro](https://github.com/adobe-fonts/source-code-pro/raw/release/LICENSE.md) and
[Ubuntu Mono](https://github.com/braver/programmingfonts/raw/gh-pages/fonts/resources/ubuntu/license.txt).
