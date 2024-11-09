
##########
Change Log
##########

- In development.

  - 2024/11/09:

    Fix accumulating the the ``--abbrev`` command when refreshing (in some cases).

  - 2023/04/20:

    Ding when next/prev unread fail.

  - 2023/02/07:

    Report when ``magit-commit-mark-next-unread`` and ``magit-commit-mark-prev-unread``
    do not find a message. Making it clear there was nothing to do and that the operation is not taking a long time.

  - 2022/08/09:

    Add ``magit-commit-mark-on-skip-to-unread`` as a convenient way to immediately mark commits as unread.

  - 2022/07/22:
    Fix bug where the magit's timer to show a revision after motion
    would interfere with showing the next/previous unread message.

  - 2022/04/22:
    Add ``magit-commit-mark-next-unread`` and ``magit-commit-mark-prev-unread`` to support
    easily navigating to the next/previous unread commit.

  - 2022/03/15:
    Fix marking when the cursor wasn't at the beginning of the line.

  - 2022/03/11:
    Font locking should only be applied to ``magit-log-mode`` (not other magit modes).

  - 2022/01/24:
    Add ``magit-commit-mark-sha1-length`` which allows for possible increases in the SHA1 length used by Magit
    that otherwise causes those SHA1's not to match previously stored revisions.

- Version 0.1 (2021-10-22)

  Initial release.
