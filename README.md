# x11-ttf-fonts

## NAME

__x11-ttf-fonts-install__ - indexes a set of exiting monospaced fonts into ~/.local/share/fonts  
__x11-ttf-fonts-ubuntu__  - downloads and indexes the Ubuntu Mono fonts into ~/.local/share/fonts  

## SYNOPSIS

Platform Linux with X11 or Cygwin Windows with X11:

```
/bin/sh -c $(curl -fsSL https://github.com/mittelmark/x11-ttf-fonts/releases/latest/download/x11-ttf-fonts-install)
/bin/sh -c $(curl -fsSL https://github.com/mittelmark/x11-ttf-fonts/releases/latest/download/x11-ttf-fonts-ubuntu)
```

## DESCRIPTION

Installs or indexes a set of monospaced true type fonts usuable for older X11 applications like the 
[Jasspa MicroEmacs](https://github.com/bjasspa/jasspa) text editor. TrueType fonts already installed on the current
machine are linked into `~/.local/share/fonts` using the `x11-ttf-fonts-install` script. Other fonts like:

- [Anonymous Pro](https://fonts.google.com/specimen/Anonymous+Pro)
- [Courier Prime](https://github.com/quoteunquoteapps/CourierPrime/)
- [Dejavu Sans Mono](https://github.com/go-fonts/dejavu)
- [Adobe Source Code Pro](https://github.com/adobe-fonts/source-code-pro/)
- [Ubuntu Mono](https://fonts.google.com/specimen/Ubuntu+Mono)

can be as well installed if the package manager does not support installing them.

## Requirements

- Linux OS with X11 or XWayland
- MacOS with XQuartz (untested)
- Windows with Cygwin-X11 (untested)
- mkfontscale for font indexing

## Links

- [https://github.com/ProgrammingFonts/ProgrammingFonts](https://github.com/ProgrammingFonts/ProgrammingFonts)
- [https://github.com/braver/programmingfonts](https://github.com/braver/programmingfonts)
- [https://www.programmingfonts.org/ - Preview](https://www.programmingfonts.org/)

## SUPPORT

In case of problems, install suggestions for MacOS with XQuartz or suggestions for supporting other fonts use the [Issues link]() at the Github project page.

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
