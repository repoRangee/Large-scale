Changelog
#########

* 0.2.0

  * `#81`_: Added a hook to run an arbitrary script after every document is
    consumed.
  * `#98`_: Added optional environment variables for ImageMagick so that it
    doesn't explode when handling Very Large Documents or when it's just
    running on a low-memory system.  Thanks to `Florian Harr`_ for his help on
    this one.
  * `#89`_ Ported the auto-tagging code to correspondents as well.  Thanks to
    `Justin Snyman`_ for the pointers in the issue queue.
  * Added support for guessing the date from the file name along with the
    correspondent, title, and tags.  Thanks to `Tikitu de Jager`_ for his pull
    request that I took forever to merge and to `Pit`_ for his efforts on the
    regex front.
  * `#94`_: Restored support for changing the created date in the UI.  Thanks
    to `Martin Honermeyer`_ and `Tim White`_ for working with me on this.

* 0.1.1

  * Potentially **Breaking Change**: All references to "sender" in the code
    have been renamed to "correspondent" to better reflect the nature of the
    property (one could quite reasonably scan a document before sending it to
    someone.)
  * `#67`_: Rewrote the document exporter and added a new importer that allows
    for full metadata retention without depending on the file name and
    modification time.  A big thanks to `Tikitu de Jager`_, `Pit`_,
    `Florian Jung`_, and `Christopher Luu`_ for their code snippets and
    contributing conversation that lead to this change.
  * `#20`_: Added *unpaper* support to help in cleaning up the scanned image
    before it's OCR'd.  Thanks to `Pit`_ for this one.
  * `#71`_ Added (encrypted) thumbnails in anticipation of a proper UI.
  * `#68`_: Added support for using a proper config file at
    ``/etc/paperless.conf`` and modified the systemd unit files to use it.
  * Refactored the Vagrant installation process to use environment variables
    rather than asking the user to modify ``settings.py``.
  * `#44`_: Harmonise environment variable names with constant names.
  * `#60`_: Setup logging to actually use the Python native logging framework.
  * `#53`_: Fixed an annoying bug that caused ``.jpeg`` and ``.JPG`` images
    to be imported but made unavailable.

* 0.1.0

  * Docker support!  Big thanks to `Wayne Werner`_, `Brian Conn`_, and
    `Tikitu de Jager`_ for this one, and especially to `Pit`_
    who spearheadded this effort.
  * A simple REST API is in place, but it should be considered unstable.
  * Cleaned up the consumer to use temporary directories instead of a single
    scratch space.  (Thanks `Pit`_)
  * Improved the efficiency of the consumer by parsing pages more intelligently
    and introducing a threaded OCR process (thanks again `Pit`_).
  * `#45`_: Cleaned up the logic for tag matching.  Reported by `darkmatter`_.
  * `#47`_: Auto-rotate landscape documents.  Reported by `Paul`_ and fixed by
    `Pit`_.
  * `#48`_: Matching algorithms should do so on a word boundary (`darkmatter`_)
  * `#54`_: Documented the re-tagger (`zedster`_)
  * `#57`_: Make sure file is preserved on import failure (`darkmatter`_)
  * Added tox with pep8 checking

* 0.0.6

  * Added support for parallel OCR (significant work from `Pit`_)
  * Sped up the language detection (significant work from `Pit`_)
  * Added simple logging

* 0.0.5

  * Added support for image files as documents (png, jpg, gif, tiff)
  * Added a crude means of HTTP POST for document imports
  * Added IMAP mail support
  * Added a re-tagging utility
  * Documentation for the above as well as data migration

* 0.0.4

  * Added automated tagging basted on keyword matching
  * Cleaned up the document listing page
  * Removed ``User`` and ``Group`` from the admin
  * Added ``pytz`` to the list of requirements

* 0.0.3

  * Added basic tagging

* 0.0.2

  * Added language detection
  * Added datestamps to ``document_exporter``.
  * Changed ``settings.TESSERACT_LANGUAGE`` to ``settings.OCR_LANGUAGE``.

* 0.0.1

  * Initial release

.. _Brian Conn: https://github.com/TheConnMan
.. _Christopher Luu: https://github.com/nuudles
.. _Florian Jung: https://github.com/the01
.. _Tikitu de Jager: https://github.com/tikitu
.. _Paul: https://github.com/polo2ro
.. _Pit: https://github.com/pitkley
.. _Wayne Werner: https://github.com/waynew
.. _darkmatter: https://github.com/darkmatter
.. _zedster: https://github.com/zedster
.. _Martin Honermeyer: https://github.com/djmaze
.. _Tim White: https://github.com/timwhite
.. _Florian Harr: https://github.com/evils
.. _Justin Snyman: https://github.com/stringlytyped

.. _#20: https://github.com/danielquinn/paperless/issues/20
.. _#44: https://github.com/danielquinn/paperless/issues/44
.. _#45: https://github.com/danielquinn/paperless/issues/45
.. _#47: https://github.com/danielquinn/paperless/issues/47
.. _#48: https://github.com/danielquinn/paperless/issues/48
.. _#53: https://github.com/danielquinn/paperless/issues/53
.. _#54: https://github.com/danielquinn/paperless/issues/54
.. _#57: https://github.com/danielquinn/paperless/issues/57
.. _#60: https://github.com/danielquinn/paperless/issues/60
.. _#67: https://github.com/danielquinn/paperless/issues/67
.. _#68: https://github.com/danielquinn/paperless/issues/68
.. _#71: https://github.com/danielquinn/paperless/issues/71
.. _#89: https://github.com/danielquinn/paperless/issues/89
.. _#94: https://github.com/danielquinn/paperless/issues/71
.. _#98: https://github.com/danielquinn/paperless/issues/71
