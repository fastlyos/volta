
Building volta
===============

Volta should build with minimal effort.  First, make sure you've got the
dependencies installed.


Dependencies
------------

 - TinyCDB  (http://www.corpit.ru/mjt/tinycdb.html)
 - GNU make (http://www.gnu.org/software/make/)
 - Lua      (http://www.lua.org/)

If available, install these dependencies from your OS packaging system
of choice.


Compiling
---------

Just type 'make'.  Depending on your platform, GNU make may have been
installed as 'gmake' If you get any errors, try 'gmake' first.

It should build without warnings.


Installation
------------

Volta doesn't contain any installation targets.  You can put the binary
wherever makes sense on your system.  Note that it should be in a
directory that is writable to Squid, unless you plan to store the
database separately.  An example:

	mv volta /usr/local/bin
	mkdir -p /var/db/squid
	chown squid:squid /var/db/squid
	volta -f /var/db/squid/volta.db

I usually just drop it into the squid configuration directory and run it
from there.

For usage information, see the README.


Development
-----------

Volta source can be cloned via Mercurial.  The repo can be found at:

	http://code.martini.nu/volta          (primary)
	https://hg.sr.ht/~mahlon/volta       (secondary)
	https://github.com/mahlonsmith/volta (secondary)

You can use the 'debug' make target to compile a (very noisy) binary
that contains gdb symbols and perftool hooks.  Set the CPUPROFILE
environment variable to "cpu.prof" to generate a profile.

If you're hacking, you'll want these dependencies installed too.

  - ragel (http://www.complang.org/ragel/)
  - mercurial (http://mercurial.selenic.com/)
  - google-perftools (http://code.google.com/p/google-perftools/)
  - graphviz (http://www.graphviz.org/)
  - ctags (http://ctags.sourceforge.net/)

