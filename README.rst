OMERO.autotag
================
OMERO.autotag is a plugin for `OMERO.web <https://github.com/ome/omero-web>`_ that automates the application of tags to images based on the
original filename, path, and extensions of the images.

This was formerly part of [OMERO.webtagging](https://github.com/German-BioImaging/webtagging), the umbrella name for tools developed to enhance use of text annotations (tags) in OMERO.

Requirements
============

As Python 2 has now reached end-of-life, OMERO 5.6 now
requires Python 3. With release 3.1.0 of autotag, the following are now required. To use autotag on older OMERO systems (running Python 2),
please use versions older than 3.1.0.

* Python 3.5 or later
* omero-web 5.6 or later
* django 1.11 or later

User Documentation
==================

http://help.openmicroscopy.org/web-tagging.html

Installation
============

The recommended way to install autotag is using `pip`, but it is also possible
to install it manually as described `here <https://www.openmicroscopy.org/site/support/omero5/developers/Web/CreateApp.html#add-your-app-location-to-your-pythonpath>`_.

::

  # In the python environment of OMERO.web (virtualenv or global)
  pip install omero-webtagging-autotag

  # Add autotag to webclient
  omero config append omero.web.apps '"omero_webtagging_autotag"'

  # Add autotag to centre panel
  omero config append omero.web.ui.center_plugins '["Auto Tag", "omero_webtagging_autotag/auto_tag_init.js.html", "auto_tag_panel"]'


Documentation
=============

Available on the `OMERO website <http://help.openmicroscopy.org/web-tagging.html>`_.


Development
===========

Uses node and webpack.

This will detect changes and rebuild `static/autotag/js/bundle.js` when there
are any. This works in conjunction with django development server as that
will be monitoring `bundle.js` for any changes.

To build the node components on changes

::

  cd omero_webtagging_autotag
  npm install
  node_modules/webpack/bin/webpack.js --watch

To install using pip in development mode (in appropriate virtualenv)

::

  # In the top-level autotag directory containing setup.py
  pip install -e .
  cd $OMERO_PREFIX

OMERO development server can then be started in the usual way. Remember to
configure the autotag settings the same as above.

Project Maintenance
===================

I (Douglas) am no longer actively developing
OMERO.webtagging. I am thrilled to hand over
maintainence and development to
`German Bioimaging <https://gerbi-gmb.de/i3dbio/i3dbio-about/>`_.

Acknowledgements
================

OMERO.webtagging was created by Douglas P. W. Russell
(dpwrussell@gmail.com) while at Oxford University and
Harvard Medical School, then later extended by DPWR
Consulting Ltd.

These plugins were developed originally with the
support of [Micron Advanced Bioimaging Unit](https://micronoxford.com/)
funded by the Wellcome Trust Strategic Award 091911,
and [Open Microscopy](https://www.openmicroscopy.org/).

Continued development was supported by [The Laboratory
of Systems Pharmacology, Harvard Medical School](https://hits.harvard.edu/the-program/laboratory-of-systems-pharmacology/research-program/) and
[Research Computing, Harvard Medical School](https://it.hms.harvard.edu/our-services/research-computing).

Continued development was sponsored by
[Micron Advanced Bioimaging Unit](https://micronoxford.com/)
funded by the Wellcome Trust Strategic Award 107457.
