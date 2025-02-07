*****************************************************************
Improved Nano Syntax Highlighting Files For Raspbian-Stretch-Lite
*****************************************************************

This repository holds ``{lang}.nanorc`` files that have improved
definitions of syntax highlighting for various languages.

1. Copy files
~~~~~~

*System wide will look like so*::

    cd /usr/share/nano
    git init
    sudo git remote add origin https://github.com/swoopsta/nanorc.git
    sudo git fetch
    sudo git checkout -t origin/master -f


2. Configure ``nano``
~~~~~~~~~

Once there you should add the languages you want to your
nano configuration file ``~/.nanorc``.  For example::

    ## C/C++
    include "~/.nano/c.nanorc"

You can also append the contents of ``~/.nano/nanorc`` into your
``~/.nanorc`` to include all languages::

    cat ~/.nano/nanorc >> ~/.nanorc

Or to be less verbose, append content of the folder in one line with wildcard::

    ## For all users
    $ echo "include $install_path/*.nanorc" >> /etc/nanorc
    ## For current user
    $ echo "include $install_path/*.nanorc" >> ~/.nanorc

where ``$install_path`` is ``/usr/share/nano-syntax-highlighting`` or ``~/.nano/`` or ...

1a.  Automatic installer
~~~~~~~~~~~~~~~~~~~~~~
Finally, you can run an automatic installer using the following code::
c
    $ curl https://raw.githubusercontent.com/scopatz/nanorc/master/install.sh | sh

or alternatively::

    $ wget https://raw.githubusercontent.com/scopatz/nanorc/master/install.sh -O- | sh

*Note -
    some syntax definitions which exist in Nano upstream may be preferable to the ones provided by this package.
    The install.sh script may be run with ``-l`` or ``--lite`` to insert the included syntax definitions from this package
    with lower precedence than the ones provided by the standard package.


1b. Distributive specific installation via package managers
~~~~~~~~~~
On **Arch Linux** and other *pacman/aur* based systems it is possible to::

    $ aurman -S nano-syntax-highlighting-git

or search package::

    $ aurman -Ss nano-syntax-highlight

Then you need to mannually add ``.nanorc``-s to user's ``~/.nanorc`` or system ``/etc/nanorc``. See **$2**

Acknowledgement
~~~~~~~~~~~~~~~
Some of these files are derived from the original nano release [`Project <https://www.nano-editor.org/>`_] [`Repository <https://git.savannah.gnu.org/cgit/nano.git>`_]
