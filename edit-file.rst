===========
Edit a file
===========

Each page of the published documentation, such as :doc:`this very page
<edit-file>` that you're reading now on Read The Docs, is maintained in a file
in the GitHub repository for the documentation set - here's the
`RestructuredText file for this page
<https://github.com/evildmp/sphinx-rst/blob/master/edit-file.rst>`_.

There's also a :doc:`Register page <register>`, containing a list of all the
people who have done this tutorial. Now you're going to add yourself to that
page, by editing the RestructuredText source file:

* Open https://github.com/evildmp/sphinx-rst/blob/master/register.rst.
* Select the Edit this file icon.
* Before doing anything else, select *Create a new branch for this commit and
  start a pull request*.
* Add a new line at the bottom of the list, following the example of existing
  entries.
* Make sure the file ends with a blank line.
* Select the **Commit changes** button.

This will create a fork of the documentation repository in your own GitHub
account. Your changes will arrive at https://github.com/evildmp/sphinx-rst/pulls
as a *pull request*, and once accepted, will become part of the source code of
this website.

As soon as it's accepted, Read The Docs will start rebuilding the site (you can
see the `list of recent builds
<https://readthedocs.org/projects/get-started-with-sphinx-and-rst/builds/>`_)
and within a few minutes the build will have completed.

The new :doc:`Register page <register>` will contain your entry.
