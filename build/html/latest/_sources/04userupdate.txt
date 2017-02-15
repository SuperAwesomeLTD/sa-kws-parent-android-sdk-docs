Update a user
=============

You can update information for the user you're authenticated as by calling:

.. code-block:: java

  // get an existing user instance
  KWSParentUser updatedUser = existingUser;

  // update a field
  updatedUser.lastName = "Name";

  // call the following method to update a users' details
  KWSParent.sdk.update (MainActivity.this, new KWSUpdateParentInterface(){
    @Overwrite
    void didUpdateParent (boolean operationOK) {
      // handle update
    }
  });

The callback will pass the following value on completion:

=========== ==== ======
Value       Type Meaning
=========== ==== ======
operationOK Bool wether the user could be updated
=========== ==== ======
