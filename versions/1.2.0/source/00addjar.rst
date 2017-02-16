Add the SDK as a JAR library
============================

If you're running an environment which does not support Gradle, then you'll need to add the SDK manually.

You can download the following zip archive:

`KidsWebServicesParentSDK-<sdk_version>.Android.full.jars.zip <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/package/kws_parent_android/<sdk_version>/KidsWebServicesParentSDK-<sdk_version>.Android.jars.zip?raw=true>`_

The archive will contain a number of .jar files, representing the components of the SDK.
Add them to the **lib** folder in your Android project and rebuild the project.

Also, add the following permissions to your AndroidManifest.xml file:

.. code-block:: xml

    <uses-permission android:name="android.permission.INTERNET"/>

Once you've integrated the Kids Web Services Parents SDK, you can access all functionality by including:

.. code-block:: java

    import kws.superawesome.tv.kwsparentsdk.*;
