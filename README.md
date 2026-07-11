DozenOS toplevel build
===================

For the most up-to-date documentation, please read the online build guide at
[docs.dozenos.io](https://docs.dozenos.io/en/latest/contributing/build-dozenos.html).

# What is DozenOS

DozenOS is an open source operating system for network devices (routers, firewalls
and so on). If you want to use it in your network, check out download and
installation instructions at https://docs.dozenos.io/en/latest/installation/index.html

If you want to modify DozenOS and/or join its development, read on.

# About this repository

DozenOS is a GNU/Linux distribution based on Debian. Just like any other
distribution, it consists of multiple packages.

Some packages are taken from the upstream, while other are modified or written
from scratch by DozenOS developers. Every package maintained by the DozenOS team has
its own git repository. DozenOS image build is therefore a multi-step process.
Packages are compiled first, then an ISO is built from Debian packages and our
own packages.

This is the top level repository that contains links to repositories with DozenOS
specific packages (organized as Git submodules) and scripts and data that are
used for building those packages and the installation image.

# Repository Structure

There are several directories with their own purpose:

 * `build/`    Used for temporary files used for the build and for build artifacts
 * `data/`     Data required for building the ISO (e.g. boot splash/configs)
 * `packages/` This directory can hold arbitrary *.deb
               packages which will be embedded into the resulting ISO.
               Among other things those packages will be: Linux Kernel, FRR,
               Netfilter...
 * `scripts/`  Scripts that are used for the build process
 * `tools/`    Scripts that are used for maintainer's tasks automation and other
               purposes, but not during ISO build process

# Building DozenOS

In order to have a single manual and not maintining multiple copies the
instructions on how to build DozenOS either in a Docker container or natively can
be found in our [Documentation - Build DozenOS](https://docs.dozenos.io/en/latest/contributing/build-dozenos.html).

# Development Branches

The default branch that contains the most recent DozenOS code is called `rolling`.

All new code goes to the `rolling` branch. When a new LTS release is ready for feature freeze, a
new branch is created for the release, and new code from `rolling` is backported
to the release branch as needed.

Post-1.2.0 branches are named after constellations sorted by area from smallest
to largest. There are 88 of them, here's the
[complete list](https://en.wikipedia.org/wiki/IAU_designated_constellations_by_area).

Existing branches:

* DozenOS 1.4: `sagitta` (Arrow) [LTS]
* DozenOS 1.3: `equuleus` (Little Horse) [LTS]
* DozenOS 1.2: `crux` (Southern Cross) [Unsupported]

The next LTS release will be DozenOS 1.5 `circinus` (Compasses).
