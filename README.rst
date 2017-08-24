docutils
========

``docutils`` takes care of transforming files from RST to HTML.
This repository is for the ``chevah`` project.


Development
===========

Each change needs a dedicated ticket and a dedicated branch::

    $ git checkout -b TICKET_ID-short-name

Create a PR and request a review.

Once all the required tests are green and you have a review,
you can merge from GitHub's merge button.

The merge button will tell you if something is not right.


Manual tests
============

For manual tests, update ``setup.py`` to a new version like
``version="1.4.4.c13"`` then run ``python setup.py sdist`` to create the python
source package in the 'dist/' folder.

With this package, manually install it into the repo to test.
For example to test ``scame`` in the ``server`` repo:

```
cd path/to/server/repo/base
./build-OS-CPU/bin/python -m pip install -U
../path/to/scame/dist/scame-package.1.2.3.tar.gz`
paver lint --all
```

`paver lint` by default will only check the files changed since master so you
need the `--all` flag to recheck even the files which were not change.


Updating the package
====================

In order to have the change available in the other repos, the change should
come with an updated version and once merged a new package to be published.