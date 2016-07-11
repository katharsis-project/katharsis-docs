How to improve or extend Katharsis
==================================

In this guide you will find out how to contribute to Katharsis.

NOTE: This is a work in progress.

We use gitter to chat with team members `Katharsis Gitter`_ .

If you have found a bug, please submit a patch to the repository.
You'll find all of them on our `Katharsis Github`_ project.

Do you think Katharsis should do X?
-----------------------------------

If you have an idea for a new feature that Katharsis should support it is a good idea to start a discussion about it.
You can start discussions on `Katharsis Gitter`_ or create a new issue on `Katharsis Github`_ .

If you also have code for the feature, definitly submit an issue and a pull request.

Please note that it might take some time for us to answer since we are all volunteers.


How development happens
-----------------------

We use `git flow`_ to guide development. That means that branches have a special
meaning and work is integrated using conventions defined by git flow.

We use ``master`` branch to keep the latest stable version.

We use ``development`` branch to gather new features until they are mature enough to make a release.

As described in `git flow`_ new features are developed in features branches.
Once a feature is complete it should get merged in ``development`` via a ``pull request`` and ``code review``.

In time, features gatter and we can decide to make a new release.
After a ``feature freaze`` period when only bug-fixes are allowed, we can release the new version of the project.
We do this by tagging the last commit on ``development``, building binaries, publishin artifacts to Maven Central and
merging development into master to prepare for the next development cycle.

We use ``2.x.y`` style branches to keep maintenance versions. These version will not receive new features and are
kept for bugfixing and creating maintenance releases.


.. _`Katharsis Gitter`: https://gitter.im/katharsis-project/
.. _`Katharsis Github`: https://github.com/katharsis-project/
.. _`git flow`: http://nvie.com/posts/a-successful-git-branching-model/
