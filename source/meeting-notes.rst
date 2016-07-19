Meeting notes
==================================

One of the main goal of the Katharsis Team is to support the community, that is not only provide support for submitted issues and answer questions on Gitter, but also conduct weekly meetings where everyone can participate and discuss about Katharsis development and activities to make Katharsis better!

This page contains executive summary of each public meeting that had been held.

Meeting notes - 13.07.2015
------------------------------

* Framework integrations (e.g. katharsis-rs, katharsis-spring) should be merged with katharsis-core to allow easier building process
* Maven is good for Java projects, but it might be better switch to Gradle to improve project extendability and allow upload to bintray.com and Maven Central
* The documentation on the main page should redirect to readthedocs. All of the information from the current main page had been migrated except fancy graphics. Tutorials should also be included with not only about Katharsis but also JSON API. It could be good to make use of Apache projects template
* The development process should be well defined. As for now there are two processes, where the first for katharsis-vertex which uploads atrifacts to bintray.com and the second which uploads the rest of them. Since there is no Maven module configuration for Katharsis repositories, each project has to be uploaded separately.
* Deployment definitions should be removed from POMs
* Each week there should be one meeting and every one of them will end with a note
* There is a confusion about the purposes of Gitter rooms. katharsis-docs should include information what is the purpose of each room.
