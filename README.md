(This is a work-in-progress. I am developing a Jupyter Notebook with a bash kernel to demonstrate some of the packaging techniques used by HUBzero)

# HUBzero Packaging Tutorial

## Introduction
Due to the many software dependancies used throughout the HUBzero platform, there must be a mechanism used to control the various software components to make sure that bugs are patched and that deployments of production environments are uniform.

Linux operating systems have developed package managers which help manage dependancies and versioning. Much like the "App Store" paradigm most consumers are used to, these package managers contain a catalog of software that can be installed on a given system.

The concept of a Linux distribution means that an operating system is formed with the Linux kernel AND a collection of software which makes the kernel useful to an end user. The kernel does not directly make the end-user productive, it simply makes the hardware work with software. The package manager is opinionated: meaning some choices in the building and configuration of the software contained the catalog are designed to work with conventions set out by the distribution. These details are abstracted away from most end-users when a package is installed.

There are two major distributions of Linux: Debian and RedHat.

In the world of Debian, this package manager is called `aptitude` or `apt` for short, it operates from `.deb` files. In the realm of RedHat-based distribtuions, the package manager is called `yum` and uses `.rpm` files.

Although they both exist for the same reason, they are not compatable. Harkening back to the App Store paradigm: Google Maps exists for Android and iPhone, yet you cannot use the iPhone application on an Android device and vice-versa.

## Overview

Building a Debian package has been mostly automated at this point in time through the use of `m4` scaffolding, `git` versioning, and Makefiles. We will walk through building a HUBzero package using this method.

## Step 1: Clone the repository
There is a separate git repository for each package that is included in the HUBzero Platform. The repositories live on hubzero.org, but there may be plans to relocate them.

Using the `hubzero-solr` package as an example:  
`git clone gitolite@hubzero.org:hubzero/hubzero-solr`

This will clone the repository into your working directory.

*Note: I've modified the code cell below to use my work key. It's a git-fu trick to use another SSH identity than the one used by default (id_rsa) You **may** simply need to run the command documented above.*


```bash
bash -c 'ssh-add ~/.ssh/workkey;git clone gitolite@hubzero.org:hubzero/hubzero-solr test-hubzero-solr'
```

    Identity added: /home/kwojkovi/.ssh/workkey (/home/kwojkovi/.ssh/workkey)
    Cloning into 'test-hubzero-solr'...
    hubzero.org is a private system.
    All activity is monitored and may be recorded and audited.  Usage indicates 
    consent to monitoring and recording.  Unauthorized use is prohibited and subject
    to criminal and civil penalties.
    remote: Counting objects: 316, done.[K
    remote: Compressing objects: 100% (297/297), done.[K
    remote: Total 316 (delta 146), reused 0 (delta 0)[K1 MiB/s   
    Receiving objects: 100% (316/316), 190.28 MiB | 10.59 MiB/s, done.
    Resolving deltas: 100% (146/146), done.
    Checking connectivity... done.


If the above was successful, there will be output in the cell to follow.


```bash
ls -la | grep test-hubzero-solr
```

    drwxr-xr-x  4 kwojkovi kwojkovi  4096 Apr 23 21:15 test-hubzero-solr



## Further reading
* https://www.debian.org/doc/manuals/packaging-tutorial/packaging-tutorial.en.pdf


```bash

```
