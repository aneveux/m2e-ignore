m2e-ignore
==========

A simple project to copy and change to quickly build a M2E connector telling M2E to ignore a plugin's goal.

Sorry, I don't have time to provide a due-form maven archetype for now.

Things to change after checking this out
========================================

META-INF/MANIFEST.MF
--------------------

-  <code>Bundle-Name</code>: Change this to something relevant for you.
-  <code>Bundle-SymbolicName</code>: change the string before the semi-colon to match your POM's <code>artifactId</code>

build.properties
----------------

Don't touch that!


lifecycle-mapping-metadata.xml
------------------------------

This file is here to tell m2e what to do with a given maven plugin's goals
Follow the comments embedded in the file.

Note that you can copy the <code>&lt;pluginExecution&gt;</code> tag to address several plugins at once.
Each <code>&lt;pluginExecution&gt;</code> can similarly address several goals for a given plugin.

plugin.xml
----------

Don't touch either.

pom.xml
-------

You need to change the <code>artifactId</code>, <code>groupId</code> and <code>version</code> to whatever you want.

As the comments explain, you don't need to match the maven plugin's maven coordinates whatsoever.
The only think you should watch out for is to keep the <code>artifactId</code> in-sync with the <code>Bundle-SymbolicName</code> in <code>META-INF/MANIFEST.MF</code>.

Building the plugin
===================

  <code>mvn clean verify</code>

Alternatively, import your project in Eclipe and export it to a deployable Eclipse plugins.
This will create a deployable plugin for you.

