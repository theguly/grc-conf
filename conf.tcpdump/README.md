conf.tcpdump
============

This is a configuration file for tcpdump to be used with the grc (Generic Colouriser) written by Radovan Garabik.  It's purpose to to highlight and colorize tcpdump output to make it easier to read.


REQUIREMENTS
============

Python
grc
tcpdump


INSTALL
=======

The Generic Colouriser can be downloaded from: 

http://melkor.dnp.fmph.uniba.sk/~garabik/grc.html.  

The download includes two python scripts, 'grc' and 'grcat', and a number of configuration files.  To install grc, run the command:

	./install.sh

After grc in installed, copy the conf.tcpdump configuration file to the directory /usr/share/grc/.

	cp conf.tcpdump /usr/share/grc/


USAGE
=====

Of the two commands that come with grc, 'grcat' is the more useful of the two.  'grc' can be used with 'tcpdump', but it will not display the colorized output until 'tcpdump' has stop running (Ctrl-C).  An example of using grcat:

	tcpdump -nvvSi eth0 | grcat conf.tcpdump

If you would like to look at tcpdump files, the above command can be piped into 'more'.  As much as I like 'less', it displays the color escape codes and not the colorized text.

	tcpdump -nvvSr tcpdump.file | grcat conf.tcpdump | more


MODIFICATIONS
=============

Feel free to make any modifications to the configuration file that you feel is necessary.  The download for grc includes the file 'Regex.txt' that explains regular expressions in python.  The colors that are available for grc include:

none
default
bold
underline
blink
reverse
concealed
black
red
green
yellow
blue
magenta
cyan
white
on_black
on_red
on_green
on_yellow
on_blue
on_magenta
on_cyan
on_white


LIMITATIONS/PROBLEMS
====================

The regular expressions in python are a little clumsy.  You may see parts of the hex dumps or domain names get highlighted.  

I've added some highlighting in bold yellow of traffic that should not be normal, SYN-FIN packets, bad header checksums, and protocols not commonly used for example.  I've resisted the urge (not very well) to do more highlighting of attacks.  This is something that an IDS is better at.  

I am missing regular expressions for traffic that I don't currently have access to.  This includes WI-FI, IPv6, and routing protocols other than those on a default Cisco router setup.

There is a slight lag in the output.  No, I don't have a fix for it.


SUGGESTIONS
===========

Any comments or suggestions for the configuration file (this is the only thing I can take credit for), send them to Jeffrey Denton (dentonj@c2i2.com).

Any comments, suggestions, or thanks for grc, please send them to Radovan Garabik (garabik@melkor.dnp.fmph.uniba.sk).

CREDITS
=======

All credits goes to Jeff Denton, http://www.cochiselinux.org




