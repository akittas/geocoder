API Overview
============

.. _install:

Installation
~~~~~~~~~~~~

PyPi Install
------------

To install Geocoder, simply:

.. code-block:: python

    $ pip install geocoder

GitHub Install
--------------

Installing the latest version from Github:

.. code-block:: python

    $ git clone https://github.com/DenisCarriere/geocoder
    $ cd geocoder
    $ python setup.py install

Examples
~~~~~~~~

Many properties are available once the geocoder object is created.

Forward Geocoding
-----------------

.. code-block:: python

    >>> import geocoder
    >>> g = geocoder.google('Mountain View, CA')
    >>> g.geojson
    >>> g.json
    >>> g.wkt
    >>> g.osm
    ...

Reverse Geocoding
-----------------

.. code-block:: python

    >>> g = geocoder.google([45.15, -75.14], method='reverse')
    >>> g.city
    >>> g.state
    >>> g.state_long
    >>> g.country
    >>> g.country_long
    ...

House Addresses
---------------

.. code-block:: python

    >>> g = geocoder.google("453 Booth Street, Ottawa ON")
    >>> g.housenumber
    >>> g.postal
    >>> g.street
    >>> g.street_long
    ...

IP Addresses
------------

.. code-block:: python

    >>> import geocoder
    >>> g = geocoder.ip('199.7.157.0')
    >>> g = geocoder.ip('me')
    >>> g.latlng
    >>> g.city

Command Line Interface
----------------------

.. code-block:: bash

    $ geocode "Ottawa, ON"  >> ottawa.geojson
    $ geocode "Ottawa, ON" \
        --provide google \
        --out geojson \
        --method geocode