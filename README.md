docker-centos7-base
===================

Base CentOS 7 image with a few perks. This is based on
the official CentOS 7 base image.

Building this results in an updated CentOS image with
a few extra packages:

* net-tools
* tar
* wget
* unzip
* EPEL repo
* pwgen (from EPEL)

### What is it for?

Most images we find at the public Docker Hub are Ubuntu-based.
Nothing against Ubuntu, but Redhat customers fell more at home
with CentOS.

### But I need RHEL images!

Please note that nearly all images under my repository are derived from this one,
so it would be very easy to simply change the FROM clause in its
Dockerfile in order to use the RHEL 7 official base image.

The RHEL 7 official base image can be downloaded from Redhat and
installed with "docker load" and tagged with whatever name you like.

As far as I know, RHEL 7 containers are covered by its RHEL 7 hosts'
license. Yum updating should work the same way it works on the host,
but I have not been able to play with RHEL 7 yet (blame my SysAdmins).

### Useful scripts

* **build.sh** : builds the image locally (docker build)
* **runbash.sh** : convenient way to run commands on a new
  container (fast-food, auto-destroy) or even to just
  open a bash shell to play.

#### Some nice tests:

Show CentOS version:

  ./runbash.sh cat /etc/redhat=release
  CentOS Linux release 7.0.1406 (Core)

Show files (ls):

  ./runbash.sh ls -l /opt/
  total 0 

