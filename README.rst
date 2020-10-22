*******************
Veldus Sphinx Theme
*******************

.. .. image:: https://travis-ci.org/readthedocs/sphinx_veldus_theme.svg?branch=master
..    :target: https://travis-ci.org/readthedocs/sphinx_veldus_theme
..    :alt: Build Status
.. .. image:: https://readthedocs.org/projects/sphinx-rtd-theme/badge/?version=latest
..   :target: http://sphinx-rtd-theme.readthedocs.io/en/latest/?badge=latest
..   :alt: Documentation Status

.. image:: https://badge.fury.io/py/sphinx-veldus-theme.svg
    :target: https://badge.fury.io/py/sphinx-veldus-theme
    :alt: Pypi Version

.. image:: https://img.shields.io/pypi/l/sphinx_veldus_theme.svg
    :target: https://pypi.python.org/pypi/sphinx_veldus_theme/
    :alt: License

This is a fork of the official `Read the Docs`_ theme for Sphinx_. See their `theme documentation`_ for more information.

.. _Sphinx: http://www.sphinx-doc.org
.. _Read the Docs: http://www.readthedocs.org
.. _theme documentation: https://sphinx-rtd-theme.readthedocs.io/en/latest/

Installation
============

This theme is distributed on PyPI_ and can be installed with ``pip``:

.. code:: console

   $ pip install sphinx_veldus_theme

To use the theme in your Sphinx project, you will need to add the following to
your ``conf.py`` file:

.. code:: python

    import sphinx_veldus_theme

    extensions = [
        ...
        "sphinx_veldus_theme",
    ]

    html_theme = "sphinx_veldus_theme"

For more information read the full documentation on `installing the theme`_

.. _PyPI: https://pypi.python.org/pypi/sphinx_veldus_theme
.. _installing the theme: https://sphinx-rtd-theme.readthedocs.io/en/latest/installing.html

Configuration
=============

This theme is highly customizable on both the page level and on a global level.
To see all the possible configuration options, read the documentation on
`configuring the theme`_.

.. _configuring the theme: https://sphinx-rtd-theme.readthedocs.io/en/latest/configuring.html

Modifying the theme
===================

The styles for this theme use SASS_ and a custom CSS framework called Wyrm_. We
use Webpack_ and node-sass_ to build the CSS. Webpack_ is used to watch for
changes, rebuild the static assets, and rebuild the Sphinx demo documentation.

.. note::
    The installation of Node is outside the scope of this documentation. You
    will need Node version 10+ in order to make changes to this theme.

Set up your environment
-----------------------

#. Install Sphinx_ and documentation build dependencies.

   .. code:: console

       $ pip install -e '.[dev]'

#. Install Webpack_, node-sass_, and theme dependencies locally.

   .. code:: console

       $ npm install

Making changes
--------------

Changes to the theme can be compiled and tested with Webpack_:

.. code:: console

    $ npm run dev

This script will do the following:

#. Install and update any dependencies.
#. Build the static CSS from SASS source files.
#. Build the demo documentation.
#. Watch for changes to the SASS files and documentation and rebuild everything
   on any detected changes.

.. _Webpack: https://webpack.js.org/
.. _node-sass: https://github.com/sass/node-sass
.. _SASS: http://www.sass-lang.com
.. _Wyrm: http://www.github.com/snide/wyrm/

Updating PyPI
=============

After making an update to the project, you need to build, package, then update PyPI with the new updates.

Build
-----

Run the release build script:

.. code:: console

    $ npm run build

Package the build
-----------------

Find more information about packaging at the `Python Packaging User Guide`_.

.. _Python Packaging User Guide: https://packaging.python.org/tutorials/packaging-projects/

.. code:: console

    $ python3 setup.py sdist bdist_wheel

Uploading
---------

Use Twine to upload the new package to PyPi:

.. code:: console

    $ python3 -m twine upload dist/*

.. note::

    This will attempt to upload everything in your *dist/* directory. Either remove unwanted files, and change *dist/\** to be more specific.