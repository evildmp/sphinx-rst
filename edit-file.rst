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
page, by editing the RestructuredText source file.

* Open https://github.com/evildmp/sphinx-rst/blob/master/register.rst.
* Select the Edit this file icon.
* Before doing anything else, select *Create a new branch for this commit and
  start a pull request*.
* Add a new line at the bottom of the list, following the example of existing
  entries.
* Make sure the file ends with a blank line.
* Select the **Commit changes** button.

This will create a fork of the documentation repository in your own GitHub
account.

The next step is to create a pull request - a request to the maintainers to pull
the changes from the branch you've just created: select **Create pull request**.

As soon as you create the pull request, Read The Docs will start rebuilding the
site (you can see the `list of recent builds
<https://readthedocs.org/projects/get-started-with-sphinx-and-rst/builds/>`_).

If there are no errors preventing a successful build, you'll be able to view
the version of the documentation based on your branch. (If there are errors,
Read The Docs will show an error for the build; you'll have to check your
changes and edit the file again.)

Once accepted, your changes will become part of the source code of this
website. The new :doc:`Register page <register>` will contain your entry.
