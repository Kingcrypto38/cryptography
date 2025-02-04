Getting started
===============

Development dependencies
------------------------

Working on ``cryptography`` requires the installation of a small number of
development dependencies in addition to the dependencies for
:doc:`/installation` (including :ref:`Rust<installation:rust>`). These are
handled by the use of ``nox``, which can be installed with ``pip``.

.. code-block:: console

    $ # Create a virtualenv and activate it
    $ # Set up your cryptography build environment
    $ pip install nox
    $ nox -e tests-nocoverage

OpenSSL on macOS
~~~~~~~~~~~~~~~~

You must have installed `OpenSSL`_ (via `Homebrew`_ , `MacPorts`_) before
invoking ``nox`` or else pip will fail to compile.

Running tests
-------------

``cryptography`` unit tests are found in the ``tests/`` directory and are
designed to be run using `pytest`_. ``nox`` automatically invokes ``pytest``:

.. code-block:: console

    $ nox -e tests-nocoverage
    ...
    ===== 3062 passed, 61 skipped in 16.02s =====


You can also specify a subset of tests to run as positional arguments:

.. code-block:: console

    $ # run the whole x509 testsuite, plus the fernet tests
    $ nox -e tests-nocoverage -- tests/x509/ tests/test_fernet.py


.. _`Homebrew`: https://brew.sh
.. _`MacPorts`: https://www.macports.org
.. _`OpenSSL`: https://www.openssl.org
.. _`pytest`: https://pypi.org/project/pytest/
.. _`nox`: https://pypi.org/project/nox/
.. _`virtualenv`: https://pypi.org/project/virtualenv/
.. _`pip`: https://pypi.org/project/pip/
.. _`as documented here`: https://docs.rs/openssl/latest/openssl/#automatic
