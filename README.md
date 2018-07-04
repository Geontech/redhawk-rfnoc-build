Building Software Defined Radio (SDR) systems based on REDHAWK and RF-NoC
=============================================
This repository provides git submodules to setup the OpenEmbedded build system
with meta-redhawk-apps and the E310 BSP.

OpenEmbedded allows the creation of custom linux distributions for embedded
systems. It is a collection of git repositories known as *layers* each of
which provides *recipes* to build software packages as well as configuration
information.

Information about the branch names is available at
https://wiki.yoctoproject.org/wiki/Releases. Helpful articles about working
with GNUradio and Openembedded are at: http://www.opensdr.com/categories/.

Getting Started
---------------

1. Clone the git repository:

    $ git clone https://github.com/geontech/redhawk-rfnoc-build.git

2. Check out the appropriate branch:

    $ cd redhawk-rfnoc-build
    $ git checkout -b rocko origin/rocko

3. Update the submodules:

    $ git submodule update --init

4. Initialize the build system:

    $ TEMPLATECONF=`pwd`/meta-redhawk-apps/conf/ source ./openembedded-core/oe-init-build-env ./build-pi ./bitbake

5. Select the MACHINE to build for:

    $ export MACHINE=ettus-e3xx-sg1

6. Build an image:

    $ bitbake redhawk-usrp-uhd-rfnoc-image

