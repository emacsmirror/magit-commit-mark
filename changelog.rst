
##########
Change Log
##########

- In development.

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
