
#######################
Emacs Magit Commit Mark
#######################

Support for persistent marking git-commits (similar to email).

For Git users who read commits for the repositories they work on.

Available via `melpa <https://melpa.org/#/magit-commit-mark>`__.


Motivation
==========

When reading over commits for larger/active projects, it can be difficult to track which commits have been read,
especially when reading commits out-of-order.

This package supports marking commits as read/unread when viewed in ``magit-log``,
so you can tell at a glance which commits are new or need to be checked.

.. figure:: https://codeberg.org/attachments/444f1a09-1fc5-464a-80d7-3e7a00fd2ae1
   :scale: 50 %
   :align: center

   Screenshot of the magit log view.


Usage
=====

While read/unread are the main intention of this package, starred and urgent states are also supported,
which may be useful when marking commits to refer back to.

Functions
---------

``magit-commit-mark-toggle-read``
   Toggle "read" for the commit at point.
``magit-commit-mark-toggle-star``
   Toggle "star" for the commit at point.
``magit-commit-mark-toggle-urgent``
   Toggle "urgent" for the commit at point.
``magit-commit-mark-next-unread``
   Jump to the next unread commit.
``magit-commit-mark-prev-unread``
   Jump to the previous unread commit.


Customization
-------------

``magit-commit-mark-on-show-commit`` (``t``)
   Showing a commit marks it as read.

``magit-commit-mark-on-show-commit-delay`` (``2.0``)
   Delay (in seconds) before marking the commit as read (zero for instantly setting as read).

``magit-commit-mark-on-show-commit`` (``t``)
   Showing a commit marks it as read.

``magit-commit-mark-sha1-length`` (``12``)
   The number of SHA1 characters to store & use to identify commits.

   This must not be longer than the value used when displaying the log.

``magit-commit-mark-directory``
   The directory where the commit state for each repository is stored.

   When left unset ``(locate-user-emacs-file "magit-commit-mark" ".emacs-magit-commit-mark")`` is used
   to calculate the location of this file.

Faces:

``magit-commit-mark-read-face``
   The face used for read commits.
``magit-commit-mark-unread-face``
   The face used for read commits.
``magit-commit-mark-star-face``
   The face used for starred commits.
``magit-commit-mark-urgent-face``
   The face used for starred commits.

Key Bindings
------------

Key bindings will need to be set by the user, this example uses the ``;`` which is unbound by default.

.. code-block:: elisp

   (with-eval-after-load 'magit-log
     (define-key magit-log-mode-map (kbd ";") 'magit-commit-mark-toggle-read)
     (define-key magit-log-mode-map (kbd "M-;") 'magit-commit-mark-toggle-star)
     (define-key magit-log-mode-map (kbd "C-;") 'magit-commit-mark-toggle-urgent)


Details
=======

- Unique repositories are identified by their local on-disk location.
- Commit markings are stored per-repository (see ``magit-commit-mark-directory``).
- On-disk marking data is updated upon any change.


Installation
============

.. code-block:: elisp

   (use-package magit-commit-mark
     :commands (magit-commit-mark-mode))

   (eval-after-load 'magit
     (add-hook 'magit-mode-hook 'magit-commit-mark-mode))
