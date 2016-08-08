Meeting notes
==================================

One of the main goal of the Katharsis Team is to support the community, that is not only provide support for submitted issues and answer questions on Gitter, but also conduct weekly meetings where everyone can participate and discuss about Katharsis development and activities to make Katharsis better!

This page contains executive summary of each public meeting that had been held.

Meeting notes - 13.07.2016
------------------------------

* Framework integrations (e.g. katharsis-rs, katharsis-spring) should be merged with katharsis-core to allow easier building process
* Maven is good for Java projects, but it might be better switch to Gradle to improve project extendability and allow upload to bintray.com and Maven Central
* The documentation on the main page should redirect to readthedocs. All of the information from the current main page had been migrated except fancy graphics. Tutorials should also be included with not only about Katharsis but also JSON API. It could be good to make use of Apache projects template
* The development process should be well defined. As for now there are two processes, where the first for katharsis-vertex which uploads atrifacts to bintray.com and the second which uploads the rest of them. Since there is no Maven module configuration for Katharsis repositories, each project has to be uploaded separately.
* Deployment definitions should be removed from POMs
* Each week there should be one meeting and every one of them will end with a note
* There is a confusion about the purposes of Gitter rooms. katharsis-docs should include information what is the purpose of each room.

Meeting notes - 08.08.2016
------------------------------

* Create JPA integration into separate module
* Migration from Maven to Gradle can be postpone for later
* Possibilities and try to create the most suitable documentation tool and link it to the site. Consider GitBook as a possibility for keeping the documentation.
* Add automated deployment on travis from master branch that is tagged with version number
* Create contribution guide to creating issues and PRs
* Changelog should be removed from install step and move it to deploy step. Additionally release profile would be the most suitable for releasing process
* Let’s try to release version (at least bug fixing) every month to provide concise development of library and limit scope of the changes.
* For Katharsis 3 release: We should start with #53 to allow users to deserialize the document to an appriopriate format e.g. a JSON with single resource should be represented as a single resource JSON object.
* Serialization and deserialization should be split into a seprate maven module to allow future katharsis-client implemtnation without any necessary dependencies to unused code
* We should focus on solving the bugs and make a bugfixing release till the end of 14.08
