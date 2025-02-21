---
title: "Contribute code"
linkTitle: "Contribute code"
weight: 40
description: "Integrate changes into OSRD"
---

## Set things up

{{% alert color="info" %}}
Most OSRD developers use Linux. Windows and MacOS should work too, but you may run into some issues.
{{% /alert %}}

### Getting the source code

- Install [`git`](https://git-scm.com/).[^package-manager]
- Open a terminal[^git-bash] in the folder where the source code of OSRD will be located
- Run `git clone git@github.com:DGEXSolutions/osrd`

### Launch the application with docker-compose

For a long time, making changes to a component of a multi-service application involved compiling, configuring and running all services manually.

Nowadays, it can be done using `docker-compose`. You can even start only a subset of the services.

- Install `docker` and `docker-compose`. [^package-manager]
- Run `docker-compose up --build`

[^package-manager]: Under Linux, use your distribution's package manager, such as `apt-get`
[^git-bash]: Under Windows, open `Git Bash`


## Share your changes

{{% alert color="warning" %}}
The source code of OSRD is available under [the LGPLv3 license](https://choosealicense.com/licenses/lgpl-3.0/).
By contributing to the codebase, you consent to the distribution of your changes under the project's license.

LGPLv3 forbids modifying source code without sharing the changes under the same license: use other people's work, and share yours!

This constraint does not propagate through APIs: You can use OSRD as a library, framework or API server to interface with proprietary software. Please suggest changes if you need new interfaces.
{{% /alert %}}


This chapter is about the process of integrating changes into the common code base. **If you need help at any stage, open an issue or message us.**

1) If you are not used to Git, [follow this tutorial](https://learngitbranching.js.org/)

2) **Create a branch**  
If you intend to contribute regularly, you can request access to the [main repository](https://github.com/DGEXSolutions/osrd). Otherwise, [create a fork](https://github.com/DGEXSolutions/osrd/fork).

3) **Add changes to your branch**  
Before you start working, try to split your work into macroscopic steps. At the end of each stop, save your changes into a commit. Try to follow [style conventions](../conventions/).

4) **Open a pull request**  
Once your changes are ready, you have to request integration with the `dev` branch. It can be done through [the web interface](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).

5) **Take feedback into account**  
Once your pull request is open, [other contributors can review your changes](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews):
   - Any user can review your changes
   - Your code has to be approved by a contributor [familiar with the code](https://github.com/DGEXSolutions/osrd/blob/dev/.github/CODEOWNERS)
   - All users are expected to take critical comments into account
   - Comments tend to be written in an open and direct manner. The intent is to efficiently collaborate towards a solution we all agree on.
   - Once all discussions are resolved, a maintainer integrates the change.

6) **If you believe somebody forgot to review / merge your change, please speak out, multiple times if needs be.**


## Git commit style

The overall format for git commits is as follows:

```
component: imperative description of the change

Detailed description of the change and what motivates it,
if it is not entirely obvious from the title.
```

- **the commit message, just like the code, must be in english**
- all lowercase
- there can be multiple components separated by `:` in case of hierarchical relationships, with `,` otherwise
- the body of the commit should probably contain a detailed description of the change
