WWWSet
======
A small Bash script to set the DocumentRoot on a development machine to a specified directory.


Basicly this script repoints the DocumentRoot (/var/www by default) to a new directory.

It can be used implicitly to specify a new root:

	wwwset /dir/somewhere/on/disk

Or by itself:

	wwwset

to set the current directory as the root.
