
Usage
=====

**lets** can be used in a variety of different environments.

=============
Bash Terminal
=============

In a bash terminal, use ``source lets/bin/activate`` to enter the **lets virtual environment** and enable *tab-completion* of modules.

.. code-block:: bash

   $ source lets/bin/activate
   (lets) $ echo -n "abcd" | lets encode/base64 -v | lets decode/base64 -v && echo
   [+] |Base64| Running module with 4 bytes and options: {'verbose': True}
   [+] |Base64| Running module with 8 bytes and options: {'verbose': True}
   abcd
   (lets) $ lexit
   $ 

Every module has a verbose flag available by default.  With the verbose flag set, extra information is logged to stderr in a way that does not interfere with the content being passed from one module to the next.

===========
Bash Script
===========

To save time, sequences of modules that are particularly long or that often run together can be put into a bash script, or *workflow*.

.. literalinclude:: ../../workflows/sample.sh
   :language: bash

======
Python
======

If a sequence of modules requires a little more attention (like condition handling), a python script can also serve as a workflow.

.. autofunction:: lets.do

.. literalinclude:: ../../workflows/sample.py
   :language: python

Browse the *lets/modules* folder, use bash autocomplete, or check out :doc:`modules` to see what modules are available.  If you're interested in building your own modules and contributing to the framework, refer to :doc:`development`.