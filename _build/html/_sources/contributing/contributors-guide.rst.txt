###################
Contributors' Guide
###################

How can I contribute to DART?
=============================

In this section we describe how you can contribute your work to DART. As
an open-source project, we welcome and value your contributions for the
benefit of the community. You may want to get in touch with us at dart @
ucar.edu before going too far down the development path and make sure
you are not duplicating efforts.

DART development uses the public GitHub project available at
https://github.com/NCAR/DART. Before you get started on developing with
us, it’s probably a good idea to be familiar with the `GitHub
workflow <https://guides.github.com/introduction/flow/>`__. Essentially,
you should create a **fork** of the DART project, which is a publically
visible copy of the repository that you will manage. Create a **branch**
for your feature with an appropriate name for your project, and when you
are finished with your changes you can **commit** them to your fork.
After testing locally on your machine, you can push them to your fork.
*At this point, everyone can see the changes you made on your fork.*
When you are ready to begin the conversation about merging your work
into the original project (called the DART repository master), you can
create a **pull request**, which will show your changes. After reviewing
and testing your changes, the pull request will be addressed
appropriately by the DART development team.

What if I want my work to remain private until I publish?
=========================================================

Some DART users want to work on a private branch until their work is
ready for public viewing. To accommodate users with these concerns, we
describe here an additional step to temporarily "hide" sensitive code
that is intended to be eventually contributed to DART after publication.

The user interested in maintaining this privacy should create a public
fork of the DART repository as listed above and then create a
**private** repository on GitHub.com, following the steps listed here:
https://help.github.com/en/articles/create-a-repo. The name of this repo
is arbitrary. Now follow the steps at
https://help.github.com/en/articles/adding-a-remote to add the public
fork as a *remote* repository of the private repository. The remote name
here could be "public_fork" or "upstream." Follow the usual steps for
pulling/pushing to/from your private repository as in
https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes

The user can then conduct their development on the private repository,
adding additional team members as necessary.

.. note:: Only 3 collaborators are allowed on a free non-institutional private
          repository. The DART team is happy to collaborate with you on your
          private repository, but keep the 3 collaborator limit in mind if you
          are a free GitHub.com user.