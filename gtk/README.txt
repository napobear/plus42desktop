About Plus42

Plus42 is an advanced scientific programmable calculator, based on Free42.
Free42 is a complete re-implementation of the HP-42S scientific programmable
RPN calculator, which was made from 1988 until 1995 by Hewlett-Packard.
Free42 is a complete rewrite and contains no HP code whatsoever.
Plus42 builds on Free42 and adds algebraic expressions modeled after those
used on the HP-27S and HP-17B/19B; attached units and unit conversions modeled
after those used on the HP-48/49/50 series; directories for more organized
storage of programs and variables; and a larger display, with 131x64 pixels
or up to 8 lines of text.
At this time, the author supports versions that run on Android, iOS, Microsoft
Windows, MacOS, and Linux.


Installing Plus42:

Copy plus42dec (or plus42bin, or both) to wherever you want it, e.g. $HOME/bin
or /usr/local/bin, and make sure that that directory is in your PATH
environment variable.
When Plus42 runs, it will create a directory named plus42 under $XDG_DATA_HOME,
or under $HOME/.local/share if XDG_DATA_HOME is unset or empty.
In this directory, it will create three files, 'state', 'print', and 'keymap'
(the calculator's internal state, the contents of the print-out window, and the
PC keyboard map); also, if you want to use a non-standard skin with Plus42,
this directory is where you have to store the skin's layout and bitmap files.

System administrators may also make skins available to all users by storing
them in a directory named plus42 or plus42/skins, relative to one or more of
the directories in $XDG_DATA_DIRS, or /usr/local/share:/usr/share if
XDG_DATA_DIRS is unset or empty.

If you're using GNOME 3, you can create a *.desktop file. Create it as
$HOME/.local/share/applications/com.thomasokken.plus42.desktop, with contents
like this:

  [Desktop Entry]
  Comment=
  Terminal=false
  Name=Plus42
  Exec=/home/thomas/plus42/plus42dec
  Type=Application
  Icon=/home/thomas/plus42/plus42icon-128x128.xpm

Change the /home/thomas/plus42 part to where you have the plus42dec executable
and the icon.
With this file in place, click on Activities and type Plus42 in the search box;
click on the Plus42 icon that it finds, and then right-click on the Plus42 icon
that appears in the Favorites bar, and select Add to Favorites.


Uninstalling Plus42:

Remove plus42dec, plus42bin, and the $XDG_DATA_HOME/plus42 or
$HOME/.local/share/plus42 directory and its contents.


NOTE: The binary in this package was built on a PC running Ubuntu 16.04, and it
is dynamically linked against libc version 2.23, libstdc++ version 5.4.0, and
GTK+ version 3.18.9. If your system has different versions of these libraries,
the binary in this package may not work. In this case, please download the
Plus42 source package and compile Plus42 using your installation's own compiler
and libraries.


Documentation

Visit https://thomasokken.com/plus42/#doc for more information.


Keyboard Mapping

You don't have to use the mouse to press the keys of the emulated calculator
keyboard; all keys can be operated using the PC's keyboard as well. The
standard keyboard mapping is as follows:

Σ+       F1, or 'a' as in "Accumulate"
Σ-       Shift F1, or 'A' (Shift a)
1/X      F2, or 'v' as in "inVerse"
Y^X      Shift F2, or 'V' (Shift v)
√x       F3, or 'q' as in "sQuare root"
X^2      Shift F3, or 'Q' (Shift q)
LOG      F4, or 'o' as in "lOg, not ln"
10^X     Shift F4, or 'O' (Shift o)
LN       F5, or 'l' as in "Ln, not log"
E^X      Shift F5, or 'L" (Shift l)
XEQ      F6, or 'x' as in "Xeq"
GTO      Shift F6, or 'X' (Shift x), or 'g' as in "Gto"

STO      'm' as in "Memory"
COMPLEX  'M' (Shift m)
RCL      'r' as in "Rcl"
%        'R' (Shift r)
R↓       'd' as in "Down"
π        'D' (Shift d), or 'p' as in "Pi"
SIN      's' as in "Sin"
ASIN     'S' (Shift s)
COS      'c' as in "Cos"
ACOS     'C' (Shift c)
TAN      't' as in "Tan"
ATAN     'T' (Shift t)

ENTER    Enter or Return
ALPHA    Shift Enter or Shift Return
X<>Y     'w' as in "sWap"
LASTX    'W' (Shift w)
+/-      'n' as in "Negative"
MODES    'N' (Shift n)
E        'e' as in "Exponent" (duh...)
DISP     'E' (Shift e)
<-       Backspace
CLEAR    Shift Backspace

▲        CursorUp
BST      Shift CursorUp
7        '7'
SOLVER   '&' (Shift 7)
8        '8'
∫f(x)    Alt 8 (can't use Shift 8 because that's * (multiply))
9        '9'
MATRIX   '(' (Shift 9)
÷        '/'
STAT     '?' (Shift /)

▼        CursorDown
SST      Shift CursorDown
4        '4'
BASE     '$' (Shift 4)
5        '5'
CONVERT  '%' (Shift 5)
6        '6'
FLAGS    '^' (Shift 6)
×        '*'
PROB     Ctrl 8 (can't use Shift * because * is shifted itself (Shift 8))

Shift    Shift
1        '1'
ASSIGN   '!' (Shift 1)
2        '2'
CUSTOM   '@' (Shift 2)
3        '3'
PGM.FCN  '#' (Shift 3)
-        '-'
PRINT    '_' (Shift -)

EXIT     Escape
OFF      Shift Escape
0        '0'
TOP.FCN  ')' (Shift 0)
.        . or ,
SHOW     '<' or '>' (Shift . or Shift ,)
R/S      '\' (ummm... because it's close to Enter (or Return))
PRGM     '|' (Shift \)
+        '+'
CATALOG  '=' (Can't use Shift + because + is shifted itself (shift =))

In A..F mode (meaning the "A..F" submenu of the BASE menu), the PC keyboard
keys A through F are mapped to the top row of the calculator's keyboard (Σ+
through XEQ); these mappings override any other mappings that may be defined
for A through F.

In ALPHA mode, all PC keyboard keys that normally generate printable ASCII
characters, enter those characters into the ALPHA register (or to the command
argument, if a command with an alphanumeric argument is being entered). These
mappings override any other mappings that may be defined for those keys.


Customizing the Keyboard Map

The standard keyboard map is designed to work well with U.S. English keyboards.
If you use a different keyboard layout, or if you have specific preferences for
how the keys should be mapped, you can customize the keyboard map to better fit
your needs.

The keyboard map is $XDG_DATA_HOME/plus42/keymap.txt, or
$HOME/.local/share/plus42/keymap.txt is XDG_DATA_HOME is unset or empty. You
can edit this file using any text editor. For convenience, you can use the
"Edit Keyboard Map" command in the Help menu to open the keyboard map in the
default text editor. Note that after making changes to the keyboard map, you
have to exit and restart Plus42 for the changes to take effect.


What's the deal with the "Decimal" and "Binary" (plus42dec/plus42bin)?

Plus42 comes in decimal and binary versions. The two look and behave
identically; the only difference is the way they represent numbers internally.
Plus42 Decimal (plus42dec) uses the Intel Decimal Floating-Point Math Library;
it uses IEEE-754-2008 quadruple precision decimal floating point, which
consumes 16 bytes per number, and gives 34 decimal digits of precision, with
exponents ranging from -6143 to +6144.
Plus42 Binary (plus42bin) uses the PC's FPU; it represents numbers as IEEE-754
compatible double precision binary floating point, which consumes 8 bytes per
number, and gives an effective precision of nearly 16 decimal digits, with
exponents ranging from -308 to +308.
The binary version has the advantage of being much faster than the decimal
version; also, it uses less memory. However, numbers such as 0.1 (one-tenth)
cannot be represented exactly in binary, since they are repeating fractions
then. This inexactness can cause some HP-42S programs to fail.
If you understand the issues surrounding binary floating point, and you do not
rely on legacy software that may depend on the exactness of decimal fractions,
you may use Plus42 Binary and enjoy its speed advantage. If, on the other hand,
you need full HP-42S compatibility, you should use Plus42 Decimal.
If you don't fully understand the above, it is best to play safe and use
Plus42 Decimal (plus42dec).


Plus42 is (C) 2004-2025, by Thomas Okken
Contact the author at thomasokken@gmail.com
Look for updates, and versions for other operating systems, at
https://thomasokken.com/plus42/
