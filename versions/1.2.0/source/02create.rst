Creating a new user
===================

You can create a new user by calling:

.. code-block:: java

  final String email = "test@email.com";
  final String password = "testtest";

  KWSParent.sdk.createUser (MainActivity.this, email, password, new KWSParentCreateUserInterface()
  {
    @Override
    public void didCreateUser (KWSParentCreateUserStatus status) {

      switch (status) {
        case Success:
          // user was created OK
          break;
        case DuplicateUsername:
          // user email is duplicate
          break;
        case InvalidEmail:
          // invalid email
          break;
        case InvalidPassword:
          // invalid password
          break;
        case NetworkError:
          // other network error
          break;
      }
  }});

The callback will pass the following values on completion:

======= ========================= ======
Value   Type                      Meaning
======= ========================= ======
status  KWSParentCreateUserStatus End status of the operation
======= ========================= ======

The **status** parameter may have the following values:

================== ======
Value              Meaning
================== ======
Success            User was authenticated successfully
DuplicateUsername  The email is already in use
InvalidEmail       Parent email is invalid
InvalidPassword    Password is less than 8 characters
NetworkError       Other network error
================== ======

From here on you'll be able get or update parent details
