Get user details
================

To obtain information on the user you're authenticated as you'll need to call:

.. code-block:: java

  KWSParent.sdk.getParentData(MainActivity.this, new KWSGetParentInterface() {
    @Override
    public void didGetParent(KWSParentUser parent) {
      if (parent != null) {
        // parent is OK
      } else {
        // parent data was not retrieved OK
      }
    }
  });

The callback will pass the following values on completion:

======= ============= ======
Value   Type    	    Meaning
======= ============= ======
user    KWSParentUser If non-null, the SDK was able to retrieve information about a user
======= ============= ======

The **KWSUser** object has the following fields:

====================== ======= =======
Field                  Type    Meaning
====================== ======= =======
id                     Integer Unique Id of the parent
email                  String  User email
firstName              String  First name of parent
lastName               String  Last name of parent
dateOfBirth            String  Date of birth of parent
gender                 String  Either 'm' or 'f'
city                   String  City of residence
postalCode             String  Postal code of the parent
streetAddress          String  Street address of parent
country                String  Country as 2-letter code
countryName            String  Country as name
language               String  Language as 2-letter code
languageName           String  Language as name
stripeChargeId         String  Stripe Charge ID
newsletterEnabled      Boolean Whether to send newsletters
splashpageVisited      Boolean Whether user has visited KWS splash page
createdAt              String  Date of creation (in milliseconds)
====================== ======= =======
