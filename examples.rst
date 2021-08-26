:orphan:

========
Examples
========

==========
Page title
==========

Heading
=======

Sub-heading
-----------

Sub-sub-heading
~~~~~~~~~~~~~~~

Sub-sub-sub-heading
^^^^^^^^^^^^^^^^^^^

Sub-sub-sub-sub-heading
.......................

Sub-sub-sub-sub-sub-heading
'''''''''''''''''''''''''''

Ordinary paragraph text. Paragraphs are separated by empty lines.

--------

*emphasis*

**strong emphasis**

``literal``

* item
* item

  * nested item
  * nested item

* item


#. numbered item
#. numbered item

   #. nested numbered item
   #. nested numbered item

#. numbered item

--------

::

    @aperture.setter
    def aperture(self, value):
        if value == "A":
            self.exposure_control_system.mode = "Shutter priority"

        elif not 1.7 <= value <= 16:
            raise self.ApertureOutOfRange

        else:
            self.exposure_control_system.mode = "Manual"
            self.exposure_control_system.aperture_set_lever.aperture = value

        self._aperture = value

--------

.. note::

   Please turn the lights off if you are the last to leave.

   As well as ``note``, you can use ``attention``, ``caution``, ``danger``,
   ``error``, ``hint``, ``important``, ``tip``, ``warning``, ``seealso``.


.. admonition:: Security notice

   The generic ``admonition`` directive allows you to provide a title, as above.

--------

`Example <https://example.com>`_

https://example.com
