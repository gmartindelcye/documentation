GIT
===

Configure ssh to connect to Github
=======================================

Create ssh keys
~~~~~~~~~~~~~~~~

$ ```ssh-keygen -t ed25519 -C "your_email@example.com"``

if using legacy apps:

$ ```ssh-keygen -t rsa -b 4096 -C "your_email@example.com"``

Check if the ssh agent is running:

$ ```eval $(ssh-agent)``

Add private key to the agent:

$ ```ssh-add ~/.ssh/id_ed25519``

Copy public key to clipboard:

``cat ~/.ssh/id_ed25519.pub``

Commands
========

Initialize
-----------

.. code:: bash

   $ git init

Configure User and mail
---------------------------

.. code:: bash

   $ git config --global user.name "Your Name"

.. code:: bash

   $ git config --global user.email "[youremail@yourdomain.com](mailto:youremail@yourdomain.com)"

You use -global to configure on the user in your entire environment; if it is
for local repository use -local

Review configuration
~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git config --list

Add file to be controlled
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git add filename

Commit Changes
~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git commit -m "Explanation of changes message".

Review Status
~~~~~~~~~~~~~~

.. code:: bash

   $ git status

.. _indicate-new-repository-ej-on-github-to-receive-current-code:

Indicate New repository (e.g. on github) to receive current code.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git remote add <name> <url>
   $ git remote add origin https://github.com/gmartinelcye/mi_aplicacion

is the repository location e.g. github

Upload repository to main branch
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git push -u origin master

Clone repository
~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git clone https://github.com/gmartinelcye/mi_aplicacion

Checkout remote repository
~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git remote -v

Get updated version of remote repository
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git pull

Review commit log

.. code:: bash

   $ git log

Compactly

.. code:: bash

   $ git log -oneline

Last N comits

.. code:: bash

   $ git log -n N

Create a new branch
~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git checkout -b <new_branch>

ó

.. code:: bash

   $ git branch <new_branch>

List Branches
~~~~~~~~~~~~

.. code:: bash

   $ git branch

Switch to a Branch
~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git checkout <branch>

Delete a Branch
~~~~~~~~~~~~~~~

.. code:: bash

   $ git branch -d <branch>

Check History in Log
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git log -graph -decorate

Join Branch to Main
~~~~~~~~~~~~~~~~~~~~~

1) Switch to main branch

.. code:: bash

   $ git checkout master

2) Join branch

.. code:: bash

   $ git merge <branch>

Retrieve remote repository after Merge
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git fetch origin master

Apply the merge to our repository
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git merge origin/master

Or we can do both steps in a single statement
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   $ git pull origin master

Rebasing
--------

Rebasing is similar to Merge but changes commit hashes

Rebasing
~~~~~~

.. code:: bash

   git rebase master

Make the repository's head its own master.

Rebase Interactive
~~~~~~~~~~~~~~~~~~

Can merge consecutive commits into one

.. code:: bash

   $ git rebase -i HEAD~4

Joins the last four commits

Revert Commits
----------------

Revert
~~~~~~~~

.. code:: bash

   $ git revert <hash-commit>

Create a commit that removes the changes

Reset
~~~~~

**Smooth:** keeps the changes:

.. code:: bash

   $ git reset -soft HEAD~1

**Hard:** removes changes

.. code:: bash

   $ git reset -hard HEAD~1

Stash

Save changes to the stash area

.. code:: bash

   $ git stash

Retrieve modifications

.. code:: bash

   $ git stash pop 

retrieves those modifications

List stash:

.. code:: bash

   $ git stash list

View modified files in a specific stash:

.. code:: bash

   $ git stash show stash@{1}

Extract a specific stash:

.. code:: bash

   $ git stash pop stash{1}

Recovering from Errors
------------------------

If you do a hard rest and want to recover you can check the "whole" history of the
history of the repository with the command:

.. code:: bash

   $ git reflog

For example if we delete the last commit and we need to recover it
we can:

.. code:: bash

   $ git reset -hard <hash-commit_deleted>

**NOTE:** *git log* only lists the commits while *git reflog* shows the repository status.
shows the repository status.

Translated with www.DeepL.com/Translator (free version)