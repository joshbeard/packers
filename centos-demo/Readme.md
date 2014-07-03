# Packer Demo

## Overview

This is a demo for reference of a simple Packer image.

It will build a CentOS 6.5 (64) VMware and VirtualBox image from an ISO, along
with a Vagrant box for each.

## Usage

To build the machines, simply execute:

```shell
packer build demo.json
```

### Results

This should produce 4 artifacts in the `output` directory:

* `packer-centos-6.5-x86_64-vmware/`: A VMware image
* `packer_vmware-iso_vmware.box`: A VMware Vagrant box
* `packer-centos-6.5-x86_64-virtualbox/`: A VirtualBox image
* `packer_virtualbox-iso_virtualbox.box`: A VirtualBox Vagrant box

## Files

**`demo.json`**

This is the `template`.  This defines what images we want to build and how
they get built.

**`http/`**

Packer provides a local HTTP server for building that can be used, for instance,
to provide kickstart or preseed files.  The HTTP service's webroot is this
directory.

**`http/centos-6.5/ks.cfg`**

This is the kickstart file for building the CentOS images.

**`scripts/`**

Directory containing various simple scripts for provisioning the CentOS image
we're building in this demo.

## References

[Packer website](http://www.packer.io/)

## Contact

Josh Beard (<josh@signalboxes.net>)
