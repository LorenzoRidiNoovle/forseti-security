---
title: Branch Methodology
order: 003
---

#  {{ page.title }}

This page describes the branches in the Forseti repo and how they're used.

In general, Forseti branches will be prefixed with a version number.
All active feature developments should be completed in the branch with the
highest-versioned numbering.  Lower-versioned branches will denote
support-basis, and only bug fixes will be accepted.

## Branches

The branches listed below are the main branches you'll use to inspect
the correct codebase or create a Pull Request (PR).

* `dev`: development branch for Forseti 1.0 (deprecated, bug fixes only).
* `master`: latest stable release for Forseti 1.0.
* `forsetisecurity.org`: documentations for Forseti 1.0 website.

* `2.0-dev`: development branch for Forseti 2.0 (GA, active development).
* `2.0-master`: latest stable release for Forseti 2.0.
* `2.0-forsetisecurity.org-dev`: documentations for Forseti 2.0 website.

A development branch is the starting point where you can create a new PR,
and where the PR will be merged into the codebase after code review. Although
there are unit tests, the development branch is still considered to be unstable
because functional and system tests are not yet complete.

A master branch is checkpointed code from the development branch that
has passed functional and system tests. The master branch is considered
to be stable and suitable for production-use.

Other active branches in the Forseti repo are those created by other developers
to contribute to Forseti. You can generally disregard any branches that aren't
explicitly listed above.

## Branching Methodology

Forseti versions are denoted with X.Y.Z version numbering schema.
X signifies architectural changes.
Y signifies database schema changes.
Z signifies code changes.

The process below outlines how major new X.0.0 versions are managed.

1. We will increment the highest-versioned development branch and create
a new development branch.<br />
```2.0-dev --> 3.0-dev```

1. Along the way, we will create the corresponding release candidates branches
for early user evaluations.<br />
```3.0-dev --> 3.0-rc1 --> 3.0-rc2```

1. When all the launch gates have been passed, we will create the GA master
branch.<br />
```3.0-rc2 --> 3.0-master```

1. After the support period has passed, the previous version dev/master branches
are deleted.

The process below outlines how minor new 0.Y.Z point versions are managed.

1. When a new point version is ready to be released, either new 0.Y.0 version
or new 0.0.Z version, a new release branch will be created from the 
appropriate dev branch.

1. The release branch will undergo functional and integration testing.
If any bug is found, a new feature branch is created from the release branch,
go through code review, and merged back into the release branch.

1. When the release branch is fully qualified, the branch is merged into 
the appropriate master and dev branch.

1. The release branch is deleted.

## What's Next

* Learn how to [submit a Pull Request](https://github.com/GoogleCloudPlatform/forseti-security/blob/master/.github/CONTRIBUTING.md).
* Learn about Forseti release process (TBD).