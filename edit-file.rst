===========
Edit a file
===========

Each page of the published documentation on Read The Docs is maintained in a
file in the GitHub repository for the documentation set.

The :doc:`Register page <register>` contains a list of all the people who have
done this tutorial. Now you're going to add yourself to that page, by editing
the reStructuredText source file.


Make the changes
================

#. Open https://github.com/evildmp/sphinx-rst/blob/master/register.rst.
#. Select the *Edit this file* icon:

   .. image:: images/edit-file.png
      :alt: Alternative text

#. Select *Create a new branch for this commit and start a pull request*.
#. Add a new entry at the bottom of the list containing the date and a link to
   your GitHub username (and optionally your own name). Follow the pattern of
   existing entries::

       * YYYY-MM-DD `username <https://github.com/username>`_ Your Name

   (Note the underscore at the end of the hyperlink markup.)

#. Make sure the file ends with a blank line.
#. Select the **Propose changes** button.

This will create a fork of the documentation repository in your own GitHub
account.


Make a pull request
===================

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


What's next
===========

This is all you need in order to contribute to documentation that's maintained
in Git, written in reStructuredText, published using Sphinx and hosted on Read
the Docs.

It's good enough for lightweight maintenance and small fixes. For more
substantial documentation contributions, it's much more effective to work
locally - writing, building and testing the documentation - then to push work
to the Git repository.

The next section covers the elements of that workflow, step-by-step.
