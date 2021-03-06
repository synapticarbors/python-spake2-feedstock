About spake2
============

Home: https://github.com/warner/python-spake2

Package license: MIT

Feedstock license: BSD 3-Clause

Summary: This library implements the SPAKE2 password-authenticated key exchange ("PAKE") algorithm. 

This library implements the SPAKE2 password-authenticated key exchange ("PAKE") algorithm. This allows two parties, who share a weak password, to safely derive a strong shared secret (and therefore build an encrypted+authenticated channel). A passive attacker who eavesdrops on the connection learns no information about the password or the generated secret. An active attacker (man-in-the-middle) gets exactly one guess at the password, and unless they get it right, they learn no information about the password or the generated secret. Each execution of the protocol enables one guess. The use of a weak password is made safer by the rate-limiting of guesses: no off-line dictionary attack is available to the network-level attacker, and the protocol does not depend upon having previously-established confidentiality of the network (unlike e.g. sending a plaintext password over TLS). The protocol requires the exchange of one pair of messages, so only one round trip is necessary to establish the session key. If key-confirmation is necessary, that will require a second round trip. All messages are bytestrings. For the default security level (using the Ed25519 elliptic curve, roughly equivalent to an 128-bit symmetric key), the message is 33 bytes long.


Current build status
====================

All platforms:
[![noarch](https://img.shields.io/circleci/project/github/conda-forge/python-spake2-feedstock/master.svg?label=noarch)](https://circleci.com/gh/conda-forge/python-spake2-feedstock)

Current release info
====================

| Name | Downloads | Version | Platforms |
| --- | --- | --- | --- |
| [![Conda Recipe](https://img.shields.io/badge/recipe-spake2-green.svg)](https://anaconda.org/conda-forge/spake2) | [![Conda Downloads](https://img.shields.io/conda/dn/conda-forge/spake2.svg)](https://anaconda.org/conda-forge/spake2) | [![Conda Version](https://img.shields.io/conda/vn/conda-forge/spake2.svg)](https://anaconda.org/conda-forge/spake2) | [![Conda Platforms](https://img.shields.io/conda/pn/conda-forge/spake2.svg)](https://anaconda.org/conda-forge/spake2) |

Installing spake2
=================

Installing `spake2` from the `conda-forge` channel can be achieved by adding `conda-forge` to your channels with:

```
conda config --add channels conda-forge
```

Once the `conda-forge` channel has been enabled, `spake2` can be installed with:

```
conda install spake2
```

It is possible to list all of the versions of `spake2` available on your platform with:

```
conda search spake2 --channel conda-forge
```


About conda-forge
=================

conda-forge is a community-led conda channel of installable packages.
In order to provide high-quality builds, the process has been automated into the
conda-forge GitHub organization. The conda-forge organization contains one repository
for each of the installable packages. Such a repository is known as a *feedstock*.

A feedstock is made up of a conda recipe (the instructions on what and how to build
the package) and the necessary configurations for automatic building using freely
available continuous integration services. Thanks to the awesome service provided by
[CircleCI](https://circleci.com/), [AppVeyor](http://www.appveyor.com/)
and [TravisCI](https://travis-ci.org/) it is possible to build and upload installable
packages to the [conda-forge](https://anaconda.org/conda-forge)
[Anaconda-Cloud](http://docs.anaconda.org/) channel for Linux, Windows and OSX respectively.

To manage the continuous integration and simplify feedstock maintenance
[conda-smithy](http://github.com/conda-forge/conda-smithy) has been developed.
Using the ``conda-forge.yml`` within this repository, it is possible to re-render all of
this feedstock's supporting files (e.g. the CI configuration files) with ``conda smithy rerender``.

For more information please check the [conda-forge documentation](https://conda-forge.org/docs/).

Terminology
===========

**feedstock** - the conda recipe (raw material), supporting scripts and CI configuration.

**conda-smithy** - the tool which helps orchestrate the feedstock.
                   Its primary use is in the construction of the CI ``.yml`` files
                   and simplify the management of *many* feedstocks.

**conda-forge** - the place where the feedstock and smithy live and work to
                  produce the finished article (built conda distributions)


Updating spake2-feedstock
=========================

If you would like to improve the spake2 recipe or build a new
package version, please fork this repository and submit a PR. Upon submission,
your changes will be run on the appropriate platforms to give the reviewer an
opportunity to confirm that the changes result in a successful build. Once
merged, the recipe will be re-built and uploaded automatically to the
`conda-forge` channel, whereupon the built conda packages will be available for
everybody to install and use from the `conda-forge` channel.
Note that all branches in the conda-forge/spake2-feedstock are
immediately built and any created packages are uploaded, so PRs should be based
on branches in forks and branches in the main repository should only be used to
build distinct package versions.

In order to produce a uniquely identifiable distribution:
 * If the version of a package **is not** being increased, please add or increase
   the [``build/number``](http://conda.pydata.org/docs/building/meta-yaml.html#build-number-and-string).
 * If the version of a package **is** being increased, please remember to return
   the [``build/number``](http://conda.pydata.org/docs/building/meta-yaml.html#build-number-and-string)
   back to 0.