=====================================
Improve the way your project is built
=====================================

Auto-build the documentation
=============================

Running ``make html`` each time you want to rebuild the documentation is
tedious. It's much more elegant to have it rebuilt for you, and refreshed in
the browser automatically on each change. `sphinx-autobuild
<https://github.com/executablebooks/sphinx-autobuild>`_ will do this for you.

.. code-block:: bash

    pip install sphinx-autobuild
    sphinx-autobuild . _build/html

Your documentation is now served at http://127.0.0.1:8000.

Even better, edit the ``Makefile``. Add::

    run:
    	sphinx-autobuild "$(SOURCEDIR)" "$(BUILDDIR)"

to it. Now you can start the server with ``make run``.

..  important::

    A ``Makefile`` uses tabs, not spaces, for indentation. If you run into an error::

        Makefile:23: *** missing separator.  Stop.

    you have probably indented your lines with spaces rather than a tab.


Build in spelling checks
========================

:doc:`sphinxcontrib-spelling <spelling:index>` will check spelling for you.

.. code-block:: bash

    pip install sphinxcontrib-spelling

It installs PyEnchant as a dependency, which in turn requires the `Enchant C library
<https://abiword.github.io/enchant/>`_. Install this - for example (in various Linuxes):

.. code-block:: bash

    apt-get install enchant

or (macOS with Brew)::

    brew install enchant

Add ``sphinxcontrib-spelling`` to your project's extensions:

.. code-block::
   :emphasize-lines: 3

    extensions = [
        [...]
        'sphinxcontrib.spelling',
   ]

The default language is US English, but you can set your own::

    spelling_lang = 'en_GB'


and run a spelling check:

.. code-block:: bash

    sphinx-build -b spelling . _build

It will list what it thinks are misspelled words. Add false positives that it
should ignore to the project's dictionary, ``spelling_wordlist.txt``.

You can also add a ``make spelling`` command to the ``Makefile``::

    spelling:
    	sphinx-build -b spelling "$(SOURCEDIR)" "$(BUILDDIR)"


Make your documentation easier for others to use
================================================

You probably want other people to be able to work on your documentation too.
They'll need to set up a virtual environment for it - but you can get the
``Makefile`` to automate most of the work.

You should have a list variables being assigned near the top of the ``Makefile``.
Add a new one:

..  code-block::
    :emphasize-lines: 5

    SPHINXOPTS    ?=
    SPHINXBUILD   ?= sphinx-build
    SOURCEDIR     = .
    BUILDDIR      = _build
    VENV          = sphinxenv/bin/activate

Add a new ``install`` command::

    install:
    	@echo "... setting up virtualenv"
    	python3 -m venv sphinxenv
    	. $(VENV); pip install --upgrade -r requirements.txt

    	@echo "\n" \
    	  "--------------------------------------------------------------- \n" \
          "* watch, build and serve the documentation: make run \n" \
    	  "* check spelling: make spelling \n" \
    	  "\n" \
          "enchant must be installed in order for pyenchant (and therefore \n" \
    	  "spelling checks) to work. \n" \
    	  "--------------------------------------------------------------- \n"

Then copy all the installed Python dependencies in the virtual environment into
a ``requirements.txt`` file::

    pip freeze > requirements.txt

Now run::

    make install

It should create the virtual environment and install all the requirements in it.

Now, we want that virtual environment to be activated for the ``run`` and ``spelling``
commands too, so edit them appropriately, so that they run their instructions inside
this virtual environment:

..  code-block::
    :emphasize-lines: 2, 5

    run:
    	. $(VENV); sphinx-autobuild "$(SOURCEDIR)" "$(BUILDDIR)"

    spelling:
    	. $(VENV); sphinx-build -b spelling "$(SOURCEDIR)" "$(BUILDDIR)"

Quieten Sphinx
==============

Sphinx's output in the console will be rather noisy - that's because right now, it's actually
processing everything in the ``sphinxenv`` virtual environment created inside your documentation
project, wholly unnecessarily.

To tell it not to, edit the ``exclude_patterns`` variable in ``conf.py``, so that it excludes the
virtual environment too::

    exclude_patterns = ['_build', 'Thumbs.db', '.DS_Store', 'sphinxenv']
