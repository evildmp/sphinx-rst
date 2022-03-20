====================
Publish your project
====================

The final step is to publish your project. This section assumes you're using
GitHub; any differences with GitLab or other services are minor.


Push your project to a Git host
===============================

Initialise the project as a Git repository:

.. code-block:: bash

    git init .

Add a ``.gitignore`` file, containing at least::

    _build
    sphinxenv

and any other file patterns you want to exclude.

For the sake of repeatability, collect all the Python dependencies in the
environment into a ``requirements.txt`` file:

.. code-block:: bash

    pip freeze > requirements.txt

Add a readme or licence file according to taste.

Create a repository at the Git hosting service, commit your local changes and
push.


Connect the project to Read the Docs
====================================

For this to work, your Git project must be public, unless you have a paid-for
Read the Docs subscription.

Log in or sign up at https://readthedocs.org.

Connect your RTD account to your GitHub account - check this at
https://readthedocs.org/accounts/social/connections/.

Use `Import a project <https://readthedocs.org/dashboard/import/?>`_ to select
your documentation repository, or else enter its details manually at
https://readthedocs.org/dashboard/import/.

When you hit **Next**, RTD will set up a webhook on your repository (Repository
> Settings > Webhooks). Now any new commits landing in the repository will
trigger a build on RTD, and the documentation will be available to view.


Adjust documentation settings
=============================

The project dashboard has an **Admin** view, with some useful settings. Some of
these are obvious, others that are worth checking include:

* *Advanced*

  * *Single version*: useful if this is a standalone documentation set, rather than
    something that's part of a versioned code-base.
  * *Build pull requests for this project*: if you expect contributions and
    would like contributors' pull requests to create their own builds.
  * *Documentation type*: set this to *SphinHTMLDir*, so that your pages'
    URLs don't include the ``.html`` extension.

* *Integrations*: to check the GitHub webhook.

