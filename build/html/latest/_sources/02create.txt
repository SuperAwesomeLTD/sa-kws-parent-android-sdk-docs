Creating a new user
===================

You can create a new user by calling:

.. code-block:: java

  final String email = "test@email.com";
  final String password = "testtest";

  KWSParent.sdk.create (MainActivity.this, email, password, new KWSCreateParentInterface()
  {
    @Override
    public void didCreateParent(KWSCreateParentStatus status) {

      switch (status) {
        case CREATED:
          // user was created OK
          break;
        case DUPLICATE:
          // user email is duplicate
          break;
        case INVALID_EMAIL:
          // invalid email
          break;
        case INVALID_PASSWORD:
          // invalid password
          break;
        case NETWORK_ERROR:
          // other network error
          break;
      }
  }});

The callback will pass the following values on completion:

======= ===================== ======
Value   Type                  Meaning
======= ===================== ======
status  KWSCreateParentStatus End status of the operation
======= ===================== ======

The **status** parameter may have the following values:

================== ======
Value              Meaning
================== ======
CREATED            User was authenticated successfully
DUPLICATE    	     The email is already in use
INVALID_EMAIL      Parent email is invalid
INVALID_PASSWORD   Password is less than 8 characters
NETWORK_ERROR      Other network error
================== ======

From here on you'll be able get or update parent details
