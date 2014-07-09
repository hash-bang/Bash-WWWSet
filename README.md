WWWSet
======
A small Bash script to switch between Apache / NodeJS (with Gulp) projects.


Basicly this script repoints the DocumentRoot (/var/www by default) to a new directory if using Apache or boots Gulp if a `gulpfile.js` is detected (see project types).

It can be used implicitly to specify a new root:

	wwwset /dir/somewhere/on/disk

Or by itself:

	wwwset

to set the current directory as the root.

Installing
----------

	git clone https://github.com/hash-bang/Bash-WWWSet.git
	cd Bash-WWWSet
	sudo make install


Project types
=============

Apache projects
---------------
This project will auto set the DocumentRoot directory to whichever directory it is given.

In most cases this means setting the `/var/www` directory to the project folder.


Gulp projects
-------------
If a `gulpfile.js` file is found within the project directory this script will stop Apache and boot Gulp to serve the package.

In order to get your Node project running on port 80 you will need to change the port its served on (duh!) and also give Node permissions to run on low ports (anything <1024):

	sudo apt-get install -y libcap2-bin
	sudo setcap cap_net_bind_service=+ep /usr/bin/nodejs
