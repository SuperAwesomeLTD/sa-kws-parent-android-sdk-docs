Login as a user
===============

To login as a parent user you'll have to call:

.. code-block:: java

  final String email = "test@email.com";
  final String password = "testtest";

  KWSParent.sdk.loginUser (this, email, password, new KWSParentLoginUserInterface() {
    @Override
    public void didLoginUser (boolean operationOK) {
      if (operationOK) {
        // logged in successfully
      } else {
        // failed to login
      }
    }
  });

The callback will pass the following values on completion:

=========== ======= ======
Value  	    Type    Meaning
=========== ======= ======
operationOK Boolean Login operation was successful
=========== ======= ======

From here on you'll be able get or update parent details
