m2e-ignore
==========

A simple project to copy and change to quickly build a M2E connector telling M2E to ignore a plugin's goal.

Sorry, I don't have time to provide a due-form maven archetype for now.

Things to change after checking this out
========================================

META-INF/MANIFEST.MF
--------------------

  Bundle-Name: Change this to something relevant for you.
  Bundle-SymbolicName: change the string before the semi-colon to match your POM's artifactId

build.properties
----------------

Don't touch that!


lifecycle-mapping-metadata.xml
------------------------------

This file is here to tell m2e what to do with a given maven plugin's goals
Follow the comments embedded in the file.

Note that you can copy the <pluginExecution> tag to address several plugins at once.
Each <pluginExecution> can similarly address several goals for a given plugin.

plugin.xml
----------

Don't touch either.

pom.xml
-------

You need to change the artifactId, groupId and version to whatever you want.
As the comments explain, you don't need to match the maven plugin's maven coordinates whatsoever.
The only think you should watch out for is to keep the artifactId in-sync with the Bundle-SymbolicName in META-INF/MANIFEST.MF.

Building the plugin
===================

  mvn clean verify

Alternatively, import your project in Eclipe and export it to a deployable Eclipse plugins.
This will create a deployable plugin for you.

