Overview
========

The Kids Web Services Parents SDK is designed to be as simple as possible while also enabling you to perform as many actions as possible.
It's built on top of the KWS API and tries to manage the complexity of interacting with it, as well as provide additional device specific features.

.. note::

	When using the SDK you will have to first authenticate as a user with the Kids Web Services back-end to be able to access the complete SDK functionality.

The Kids Web Services Parents SDK will then handle the following topics on your behalf:

+------------------------------------------------------+
| Create a new parent user                             |
+------------------------------------------------------+
| Login or logout as a user                            |
+------------------------------------------------------+
| Obtain parent data                                   |
+------------------------------------------------------+
| Update parent data                                   |
+------------------------------------------------------+

The SDK is built around a common singleton class called **KWSParent**. The singleton accessor method is simply called **sdk**.

Thus any method call will have the following pattern:

.. code-block:: java

  KWSParent.sdk.methodCall ();

Since most operations performed by the SDK involve doing network requests on KWS API, most method calls won't have a return type but will
instead require a callback, defined as an Java interface with a variable number of parameters.

.. code-block:: java

  KWSParent.sdk.methodCall (new KWSInterface () {
    @Overwrite
    void response (bool result) {
      // handle result
    }
  });

Some methods also can have one or two parameters. In this case they will have the following signature:

.. code-block:: java

  KWSParent.sdk.methodCall(int parm1, String param2, new KWSInterface () {
    @Overwrite
    void response (bool result) {
      // handle result
    }
  });

.. note::

  All callback interfaces in the Kids Web Services Parent SDK will only have one method call, thus making them suitable for Java 8 and Lambda notation.
