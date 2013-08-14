=============================
 Transifex Command-Line Tool
=============================

The Transifex Command-line Client is a command line tool that enables
you to easily manage your translations within a project without the need
of an elaborate UI system.

You can use the command line client to easily create new resources, map
locale files to translations and synchronize your Transifex project with
your local repository and vice verca. Translators and localization
managers can also use it to handle large volumes of translation files
easily and without much hassle.

Check the full documentation at
http://help.transifex.com/user-guide/client/


Installing
==========

You can install the latest version of transifex-client running

``pip install git+https://github.com/tymofij/transifex-client.git@adofex#egg=transifex-client``

Usage
=====

Initialize directory:

``tx init --host=http://beta.babelzilla.org``

Get project scheme:

``tx set --auto-remote http://beta.babelzilla.org/projects/p/PROJECT/ --file-filter="<lang>/%(name)s"``
file-filter is the shema for files, so set it to your liking.
Besides Resource's name referenced as %(name)s there are:

* %(proj)s - Projects's slug
* %(res)s - Resource's slug
* %(extension)s - Resource's extension

Pull source locale:

``tx pull -s``

Pull all locales:

``tx pull -a``

Pull some locale

``tx pull -l LANG_CODE``

While pulling you can specify download mode as --mode=skipped (empty or replaced).
Replace is the default one. Be sure not to download and then push replaced translations.
They will be marked as 100% translated then.

After you have done some editing, you can send changes to the server.

Push source:

``tx push -s``

Translations:

``tx push -t``

One translation:

``tx push -t -l LANG_CODE``
